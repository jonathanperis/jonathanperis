# Tech Stack

> A map of languages, frameworks, and tools used across the public projects

## Languages

| Language | Projects | Role |
|----------|----------|------|
| **C#** | cpnucleo, csharpc, blazor-mudblazor-starter | Primary language -- backend labs, an LLVM front-end, Blazor UI |
| **C** | super-mango-editor, solar-system-simulator | Games and orbital simulation with raylib and WebAssembly |
| **Bend 2** | jonlib | Graphics and math library working toward raylib parity |
| **TypeScript** | speedy-bird-lynx, jonathanperis.github.io | ReactLynx game and the Astro portfolio |
| **Python** | jonlib, super-mango-editor, solar-system-simulator, cpnucleo, csharpc | Tooling and tests alongside the C, C#, and Bend sources |
| **PLpgSQL** | cpnucleo | PostgreSQL functions in the .NET lab |
| **Shell** | cpnucleo, csharpc, jonlib | Build scripts, Docker entrypoints |

## Backend Frameworks

| Framework | Language | Used In |
|-----------|----------|---------|
| **FastEndpoints** | C# | cpnucleo |
| **gRPC** | C# | cpnucleo |

## Frontend Frameworks

| Framework | Used In |
|-----------|---------|
| **Blazor WebAssembly** | cpnucleo |
| **Blazor Server** | blazor-mudblazor-starter |
| **MudBlazor** | cpnucleo, blazor-mudblazor-starter |
| **Astro** | jonathanperis.github.io, cpnucleo |
| **React** | jonathanperis.github.io |
| **ReactLynx** | speedy-bird-lynx |
| **Tailwind CSS** | jonathanperis.github.io |

## Data Layer

| Technology | Purpose | Used In |
|------------|---------|---------|
| **Entity Framework Core** | ORM for writes | cpnucleo |
| **Dapper** | Micro-ORM for reads | cpnucleo |
| **PostgreSQL** | Primary database | cpnucleo |
| **SQLite** | Local persistence | blazor-mudblazor-starter |

## Infrastructure & DevOps

| Tool | Purpose |
|------|---------|
| **Docker** | Containerization across backend and learning labs |
| **Docker Compose** | Multi-container orchestration |
| **GitHub Actions** | CI/CD pipelines |
| **GitHub Pages** | Static site hosting for the portfolio and project demos |

## Observability

| Tool | Purpose | Used In |
|------|---------|---------|
| **OpenTelemetry** | Distributed tracing and metrics | cpnucleo |

## Game Development

| Tool | Purpose |
|------|---------|
| **raylib** | Cross-platform graphics, input, and audio |
| **Emscripten** | C to WebAssembly compilation |
| **Makefile** | Build system for the C projects |

## Compilers

| Tool | Purpose | Used In |
|------|---------|---------|
| **Roslyn** | C# parsing and compilation front-end | csharpc |
| **LLVM** | Native code generation | csharpc |

## .NET-Specific Practices

Techniques used across .NET projects:

- **Native AOT** -- ahead-of-time compilation for small native executables
- **Source generators** -- compile-time code generation where reflection is unavailable
- **Architecture tests** -- NetArchTest enforcing layer boundaries in cpnucleo
- **Contract tests** -- executable checks that published behavior matches the lab

## Architecture Patterns

Used across the public projects:

- **Clean Architecture** (cpnucleo)
- **CQRS** -- Command Query Responsibility Segregation (cpnucleo)
- **DDD** -- Domain-Driven Design (cpnucleo)
- **Learning labs** -- readable source, repeatable experiments, and docs beside the code
