# cpnucleo

> Production-grade .NET 9 microservices reference architecture

**Repository**: [github.com/jonathanperis/cpnucleo](https://github.com/jonathanperis/cpnucleo) | **Stars**: 8 | **Language**: C#

## Overview

cpnucleo is the flagship project -- a comprehensive reference implementation demonstrating how to build production-ready microservices using .NET 9. It implements a **project management system** with organizations, projects, assignments, users, workflows, and impediment tracking.

This isn't a tutorial codebase with shortcuts. It's a living example of how enterprise .NET should look when you care about maintainability, testability, and performance.

## Architecture

### Clean Architecture Layers

```
Presentation (Blazor WASM + MudBlazor)
    |
    v
API Layer (FastEndpoints)
    |
    v
Application Layer (CQRS Commands/Queries)
    |
    v
Domain Layer (DDD Entities, Value Objects, Aggregates)
    |
    v
Infrastructure Layer (EF Core + Dapper, PostgreSQL)
```

### Key Architectural Decisions

- **CQRS via gRPC**: Commands and queries are separated at the transport level, with gRPC handling inter-service communication. This isn't CQRS theater -- reads and writes genuinely go through different paths
- **FastEndpoints over Controllers**: Minimal API-like endpoint definitions with built-in validation, organized by feature rather than by controller
- **EF Core + Dapper**: EF Core for writes (leveraging change tracking and migrations), Dapper for reads (raw performance where ORM overhead isn't justified)
- **Native AOT**: The entire stack compiles ahead-of-time, eliminating JIT startup costs and reducing memory footprint
- **Architecture Tests**: NetArchTest enforces layer dependency rules at test time -- if someone imports Infrastructure from Domain, the build breaks

### Domain Model

The system models a project management domain:
- **Organizations** -- top-level grouping
- **Projects** -- belong to organizations
- **Assignments** -- work items within projects
- **Users** -- team members with JWT-based authentication
- **Workflows** -- state machines for assignment lifecycle
- **Impediments** -- blockers tracked against assignments

### Infrastructure

- **PostgreSQL** with EF Core migrations
- **Docker** multi-stage builds with Nginx reverse proxy
- **OpenTelemetry** for distributed tracing and metrics
- **JWT authentication** with role-based access
- **Rate limiting** to protect endpoints

### Frontend

Blazor WebAssembly with MudBlazor component library, providing a Material Design UI. The WASM client communicates with the backend through the FastEndpoints API layer.

### Testing Strategy

- **Unit tests** for domain logic and application handlers
- **Integration tests** hitting real PostgreSQL instances
- **Architecture tests** with NetArchTest to enforce dependency rules

## Tech Stack

| Layer | Technology |
|-------|-----------|
| API | FastEndpoints, gRPC |
| Application | MediatR-like CQRS |
| Domain | DDD (Entities, Value Objects, Aggregates) |
| Persistence | EF Core 9, Dapper, PostgreSQL |
| Frontend | Blazor WASM, MudBlazor |
| Runtime | .NET 9, Native AOT |
| Infrastructure | Docker, Nginx, OpenTelemetry |
| Testing | xUnit, NetArchTest |

## Topics

`clean-architecture` `docker` `dotnet` `unit-testing` `blazor` `cqrs` `csharp` `ddd` `dotnet-9` `entity-framework` `fastendpoints` `grpc` `microservices` `native-aot` `postgresql`
