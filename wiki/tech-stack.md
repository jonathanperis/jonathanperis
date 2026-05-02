# Tech Stack

> A comprehensive map of languages, frameworks, and tools used across all projects

## Languages

| Language | Projects | Role |
|----------|----------|------|
| **C#** | cpnucleo, rinha2-dotnet, blazor-starter | Primary language -- backend services, microservices, Blazor UI |
| **C** | super-mango-game | Game development with SDL2 and WebAssembly |
| **Rust** | rinha2-rust | High-performance backend services |
| **Go** | rinha2-go | Lightweight API services |
| **Python** | rinha2-python, super-mango-game (tooling) | Backend services, build tooling |
| **TypeScript** | jonathanperis.github.io | Frontend with React/Next.js |
| **JavaScript** | rinha2-k6 | k6 load testing scripts |
| **PLpgSQL** | all rinha2 repos | PostgreSQL stored procedures |
| **Shell** | cpnucleo, rinha2-k6 | Build scripts, Docker entrypoints |

## Backend Frameworks

| Framework | Language | Used In |
|-----------|----------|---------|
| **ASP.NET 9** | C# | rinha2-dotnet |
| **FastEndpoints** | C# | cpnucleo |
| **gRPC** | C# | cpnucleo |
| **Actix-web 4** | Rust | rinha2-rust |
| **chi/v5** | Go | rinha2-go |

## Frontend Frameworks

| Framework | Used In |
|-----------|---------|
| **Blazor WebAssembly** | cpnucleo |
| **Blazor Server** | blazor-mudblazor-starter |
| **MudBlazor** | cpnucleo, blazor-starter |
| **React 19** | jonathanperis.github.io |
| **Next.js 16** | jonathanperis.github.io |
| **Tailwind CSS v4** | jonathanperis.github.io |

## Data Layer

| Technology | Purpose | Used In |
|------------|---------|---------|
| **Entity Framework Core 9** | ORM for writes | cpnucleo |
| **Dapper** | Micro-ORM for reads | cpnucleo |
| **Npgsql** | PostgreSQL driver (.NET) | rinha2-dotnet |
| **SQLx 0.7** | Compile-time SQL (Rust) | rinha2-rust |
| **pgx/v5** | PostgreSQL driver (Go) | rinha2-go |
| **PostgreSQL** | Primary database | all backend projects |

## Infrastructure & DevOps

| Tool | Purpose |
|------|---------|
| **Docker** | Containerization across all projects |
| **Docker Compose** | Multi-container orchestration |
| **Nginx** | Reverse proxy and load balancing |
| **GitHub Actions** | CI/CD pipelines |
| **Azure Web App** | Cloud hosting (blazor-starter) |
| **GitHub Pages** | Static site hosting (portfolio) |

## Observability

| Tool | Purpose | Used In |
|------|---------|---------|
| **OpenTelemetry** | Distributed tracing and metrics | cpnucleo, rinha2-dotnet |
| **Grafana** | Dashboard visualization | rinha2-k6 |
| **InfluxDB** | Time-series metrics storage | rinha2-k6 |
| **k6** | Load and stress testing | rinha2-k6 |

## Game Development

| Tool | Purpose |
|------|---------|
| **SDL2** | Cross-platform graphics, input, audio |
| **Emscripten** | C -> WebAssembly compilation |
| **Makefile** | Build system for C project |

## .NET-Specific Optimizations

Techniques used across .NET projects:
- **Native AOT** -- ahead-of-time compilation, no JIT
- **Trimming** -- dead code elimination
- **Source generators** -- zero-reflection JSON serialization
- **Connection pooling with multiplexing** -- Npgsql optimization
- **Architecture tests** -- NetArchTest enforcing layer boundaries

## Architecture Patterns

Used consistently across projects:
- **Clean Architecture** (cpnucleo)
- **CQRS** -- Command Query Responsibility Segregation (cpnucleo)
- **DDD** -- Domain-Driven Design (cpnucleo)
- **Microservices** (cpnucleo, all rinha2)
- **Database-first logic** -- stored procedures in PostgreSQL (all rinha2)
