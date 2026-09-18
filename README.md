[![Main Release](https://github.com/jonathanperis/jonathanperis/actions/workflows/main-release.yml/badge.svg)](https://github.com/jonathanperis/jonathanperis/actions/workflows/main-release.yml)
[![CodeQL](https://github.com/jonathanperis/jonathanperis/actions/workflows/codeql.yml/badge.svg)](https://github.com/jonathanperis/jonathanperis/actions/workflows/codeql.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

```
> "A Vinganca nunca e plena, mata a alma e a envenena." - Seu Madruga
```

```csharp
var jonathan = new Developer
{
    Location  = "Itanhaem, SP, Brazil",
    Company   = "Peris Studio",
    Focus     = new[] { "Learning by Building", ".NET", "Game Dev", "Simulation" },
    Languages = new[] { "C#", "C", "TypeScript", "Python", "Go", "Rust", "x86-64 ASM" },
    Hobbies   = new[] { "Game Dev", "Orbital Mechanics", "Load Testing Everything" }
};
```

### `$ whoami`

Software engineer building hands-on learning projects: backend systems, games, and physics simulations. I like code you can inspect, experiments you can repeat, and tradeoffs you can measure.

.NET is my backend home base. My current work also explores C11/raylib and WebAssembly, orbital mechanics, and TypeScript with Astro, React, and ReactLynx. Performance engineering connects it all: build, observe, compare, explain.

### `$ cat focus.md`

- **Learn by building:** turn working applications into guided labs, with readable source, repeatable experiments, and documentation alongside the code.
- **Explore games and physics:** build a platformer and visual level editor, then investigate numerical methods and orbital motion through native and browser simulations.
- **Compare .NET approaches:** study REST/gRPC, EF Core/Dapper, authentication, observability, and Blazor UI behavior through executable examples.
- **Make projects easy to explore:** ship playable demos, Astro documentation, and CI checks that keep published claims aligned with the implementation.

---

### `$ ls ~/projects/active`

<table>
<tr><td>

**[super-mango-editor](https://github.com/jonathanperis/super-mango-editor)** \
C11/raylib platformer, visual TOML level editor, and Sandbox School for learning game development. \
`C11` `raylib` `Emscripten` `WebAssembly` `level editor` `learning labs` \
[Play](https://jonathanperis.github.io/super-mango-editor/) · [Learn](https://jonathanperis.github.io/super-mango-editor/docs/learning-path/)

</td></tr>
<tr><td>

**[solar-system-simulator](https://github.com/jonathanperis/solar-system-simulator)** \
Physics-first orbital mechanics lab with a shared C core for native, WebAssembly, and headless runs; reproducible A/B experiments and a source-backed small-body atlas. \
`C11` `raylib` `WebAssembly` `numerical methods` `Verlet / Euler` `NASA / JPL data` \
[Simulate](https://jonathanperis.github.io/solar-system-simulator/simulator/) · [Compare experiments](https://jonathanperis.github.io/solar-system-simulator/compare/)

</td></tr>
<tr><td>

**[cpnucleo](https://github.com/jonathanperis/cpnucleo)** \
Hands-on .NET 10 project-management lab: compare REST/gRPC and EF Core/Dapper, explore architecture tradeoffs, and verify behavior with contract tests. \
`FastEndpoints` `PostgreSQL` `OpenTelemetry` `Astro` `TypeScript` `Docker` \
[Learning paths](https://jonathanperis.github.io/cpnucleo/docs/learning-lab/)

</td></tr>
<tr><td>

**[blazor-mudblazor-starter](https://github.com/jonathanperis/blazor-mudblazor-starter)** \
Local-first .NET 10 learning sandbox for Blazor Server and MudBlazor: state, forms, APIs, persistence, authentication, localization, and CSV workflows. \
`Blazor Server` `MudBlazor` `EF Core` `SQLite` `Docker` `guided labs` \
[Learning guide](https://jonathanperis.github.io/blazor-mudblazor-starter/docs/)

</td></tr>
<tr><td>

**[speedy-bird-lynx](https://github.com/jonathanperis/speedy-bird-lynx)** \
Flappy Bird-inspired arcade game exploring ReactLynx native UI: Android host, Lynx web preview, and a separate playable Canvas demo. iOS host source is a scaffold. \
`ReactLynx` `TypeScript` `Android` `Canvas` `Astro` \
[Play](https://jonathanperis.github.io/speedy-bird-lynx/) · [Docs](https://jonathanperis.github.io/speedy-bird-lynx/docs/)

</td></tr>
<tr><td>

**[jonathanperis.github.io](https://github.com/jonathanperis/jonathanperis.github.io)** \
Static portfolio and print-friendly resume, with build-time GitHub project data and a terminal-inspired UI. \
`Astro` `React` `TypeScript` `Tailwind CSS` `GitHub Pages` \
[Visit](https://jonathanperis.github.io/) · [Resume](https://jonathanperis.github.io/resume/)

</td></tr>
</table>

---

### `$ cat /proc/tech_stack`

```
+-------------------+----------------------------------------------------+
| Backend           | .NET 10, FastEndpoints, REST/gRPC, EF Core, Dapper |
| Games & physics   | C11, raylib, Emscripten, WebAssembly, TOML         |
| Web & UI          | Astro, React, ReactLynx, TypeScript, Tailwind CSS  |
| .NET UI           | Blazor Server, MudBlazor                           |
| Data & delivery   | PostgreSQL, SQLite, Docker, GitHub Actions, Bun    |
| Observability     | OpenTelemetry, Grafana, k6                         |
| Practice          | Learning labs, contract tests, reproducible runs   |
+-------------------+----------------------------------------------------+
```

---

### `$ ls ~/projects/archive/performance`

My **Rinha de Backend** repositories are archived performance experiments. They cover transaction APIs in the 2024/Q1 challenge and fraud detection in the 2026 challenge, from managed runtimes down to raw sockets and assembly.

| Challenge | Repository | What I explored |
|-----------|------------|-----------------|
| 2026 | [rinha4-back-end-dotnet](https://github.com/jonathanperis/rinha4-back-end-dotnet) | .NET 10 NativeAOT, raw HTTP/1, vector search |
| 2026 | [rinha4-back-end-c](https://github.com/jonathanperis/rinha4-back-end-c) | C, epoll, memory-mapped indexes, nearest-neighbor search |
| 2026 | [rinha4-yolo-mode](https://github.com/jonathanperis/rinha4-yolo-mode) | x86-64 assembly API and payload-derived fraud heuristics |
| 2026 | [rinha4-lb-yolo-mode](https://github.com/jonathanperis/rinha4-lb-yolo-mode) | Assembly/C load balancers, Unix sockets, SCM_RIGHTS |
| 2024/Q1 | [rinha2-back-end-dotnet](https://github.com/jonathanperis/rinha2-back-end-dotnet) | ASP.NET Core Minimal API, Native AOT, Npgsql multiplexing |
| 2024/Q1 | [rinha2-back-end-go](https://github.com/jonathanperis/rinha2-back-end-go) | Go, chi, pgx, PostgreSQL stored procedures |
| 2024/Q1 | [rinha2-back-end-rust](https://github.com/jonathanperis/rinha2-back-end-rust) | Rust, Actix-web, Tokio, SQLx |
| 2024/Q1 | [rinha2-back-end-python](https://github.com/jonathanperis/rinha2-back-end-python) | Python, Flask, Gunicorn, psycopg2 |
| 2024/Q1 | [rinha2-back-end-k6](https://github.com/jonathanperis/rinha2-back-end-k6) | Shared load harness, xk6, InfluxDB, Grafana |

The lesson I carry forward: compare correctness, latency, and resource use under explicit constraints. Benchmark reports and implementation details live with each project.

---

### `$ neofetch`

```
   jonathan@peris-studio
   ----------------------
   OS:        macOS / Linux / Docker
   Shell:     zsh + dotfiles
   Editor:    VS Code + JetBrains
   Uptime:    coding since 2015
   Loop:      build, inspect, measure, explain
   Packages:  NuGet, Bun, Cargo, pip
   Theme:     Dark Terminal Aesthetic

   Contact:   jperis.silva@gmail.com
   Portfolio: https://jonathanperis.github.io/
   Twitter:   @jperis_silva
```

---

<p align="center">
  <b><a href="https://jonathanperis.github.io/">Live demo →</a></b> | <b><a href="https://github.com/jonathanperis/jonathanperis/wiki">Documentation →</a></b>
</p>

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake.svg" />
  <img alt="github-snake" src="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake-dark.svg" width="100%" />
</picture>

---

<p align="center">
  <sub>hint: visit <a href="https://jonathanperis.github.io/">jonathanperis.github.io</a> and try the Konami code</sub>
</p>
