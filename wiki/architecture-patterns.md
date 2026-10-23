# Architecture Patterns

> Design decisions and patterns used across Jonathan's projects

## Clean Architecture (cpnucleo)

The cpnucleo project implements Clean Architecture with strict layer boundaries:

```
                    +-----------------+
                    |  Presentation   |  Blazor WASM + MudBlazor
                    +-----------------+
                           |
                    +-----------------+
                    |    API Layer    |  FastEndpoints
                    +-----------------+
                           |
                    +-----------------+
                    |   Application   |  CQRS Commands & Queries
                    +-----------------+
                           |
                    +-----------------+
                    |     Domain      |  Entities, Value Objects, Aggregates
                    +-----------------+
                           |
                    +-----------------+
                    | Infrastructure  |  EF Core, Dapper, PostgreSQL
                    +-----------------+
```

**Enforcement**: Layer dependency rules aren't just convention -- they're tested with **NetArchTest**. If a Domain class imports from Infrastructure, the test suite fails. This prevents architectural erosion over time.

**Why this matters**: Most "Clean Architecture" samples on GitHub are trivial CRUD apps where the architecture is overkill. cpnucleo is a multi-entity domain with real business rules, making the pattern actually earn its complexity.

## CQRS -- Command Query Responsibility Segregation (cpnucleo)

Commands (writes) and queries (reads) flow through separate paths:

- **Commands** go through the application layer, validated, then persisted via **EF Core** (which provides change tracking and transactional guarantees)
- **Queries** bypass the ORM and use **Dapper** for raw SQL performance
- **gRPC** is the transport layer for inter-service communication

This is CQRS done for practical reasons, not buzzword compliance. Reads and writes have genuinely different performance characteristics and optimization strategies in this system.

## Domain-Driven Design (cpnucleo)

The domain model uses DDD tactical patterns:

- **Entities** with identity and lifecycle (Users, Projects, Assignments)
- **Value Objects** for concepts without identity
- **Aggregates** defining consistency boundaries
- **Domain Events** for cross-aggregate communication

## Service Boundaries (cpnucleo)

cpnucleo uses gRPC for synchronous inter-service communication. REST and gRPC are both present so the lab can compare them, and contract tests check the behavior that comparison depends on.

## Native AOT as an Architectural Decision

Native AOT isn't just a compilation flag -- it constrains the architecture:

- No runtime reflection (rules out many ORMs and serializers)
- No dynamic assembly loading
- Source generators required for JSON serialization
- Smaller attack surface (no JIT compiler in the runtime)

csharpc is the compiler project in that direction: Roslyn is the front-end, and LLVM emits a small native executable.

## Testing Strategy

### Unit Tests

- Domain logic tested in isolation
- Application handlers tested with mocked repositories

### Integration Tests

- Hit real PostgreSQL instances
- Verify the full request pipeline

### Architecture Tests (NetArchTest)

- Enforce dependency direction (inner layers don't know about outer layers)
- Prevent Infrastructure imports in Domain
- Catch architectural violations at build time
