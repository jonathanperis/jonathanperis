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

## Database-First Logic (Rinha de Backend)

All four Rinha de Backend implementations push business logic into **PostgreSQL stored functions**. This is a deliberate architectural choice:

```sql
-- The same PLpgSQL functions are shared across C#, Rust, Go, and Python
-- The application layer is just HTTP -> validate -> call stored proc -> return
```

**Why**: For this specific workload (financial transactions requiring ACID guarantees), the database is the natural place for the logic. It eliminates network round trips, leverages PostgreSQL's transaction isolation, and reduces the application to a thin HTTP adapter. This is why all four implementations can be 140-200 lines -- they're deliberately thin.

## Microservices (cpnucleo, Rinha de Backend)

### Service Communication
- **cpnucleo**: gRPC for synchronous inter-service communication
- **Rinha de Backend**: 2 stateless API instances behind Nginx round-robin

### Infrastructure Pattern
Every multi-service project follows the same Docker Compose structure:
```
services:
  api-1:     # First API instance
  api-2:     # Second API instance
  nginx:     # Reverse proxy / load balancer
  postgres:  # Database
```

## Native AOT as an Architectural Decision

Native AOT isn't just a compilation flag -- it constrains the architecture:
- No runtime reflection (rules out many ORMs and serializers)
- No dynamic assembly loading
- Source generators required for JSON serialization
- Smaller attack surface (no JIT compiler in the runtime)

Jonathan embraces these constraints in cpnucleo and rinha2-dotnet, treating them as guardrails rather than limitations. The result is faster startup, lower memory, and a more predictable runtime.

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

### Stress Tests (k6)
- Shared test suite across all Rinha implementations
- Metrics exported to InfluxDB for Grafana visualization
- HTML reports for standalone analysis
