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
    Role      = "Software Engineer",
    Company   = "Derivative Path",
    Headline  = "Software Engineer | .NET · C# · Azure | Backend Architecture (CQRS, DDD, Microservices) | Fintech",
    Core      = new[] { "C#", ".NET", "Azure" },
    Exploring = new[] { "Rust", "Go", "Python" },
    Projects  = new[] { "Compilers", "Game Dev", "Simulation", "Bend", "C11", "WebAssembly" },
    Hobbies   = new[] { "Game Dev", "Orbital Mechanics", "Compilers" }
};
```

### `$ whoami`

Software Engineer | .NET · C# · Azure | Backend Architecture (CQRS, DDD, Microservices) | Fintech. Currently Software Engineer at Derivative Path.

12+ years of experience specializing in .NET and Fintech, with professional .NET development since May 2013. C# and .NET are the core: ASP.NET Core, Entity Framework, Azure, and backend architecture with CQRS, DDD, microservices, and clean architecture.

Actively exploring Rust, Go, and Python for high-performance and concurrent systems. Side projects are learning by building: a C# front-end for LLVM, Bend 2 graphics libraries, C11/raylib and WebAssembly, orbital mechanics, and TypeScript with Astro, React, and ReactLynx.

### `$ cat focus.md`

- **Ship fintech backends:** C# and .NET with CQRS, DDD, microservices, clean architecture, and Azure.
- **Learn by building:** side projects turn working applications into guided labs, with readable source, repeatable experiments, and documentation alongside the code.
- **Build compilers and graphics libraries:** compile C# to native code with Roslyn and LLVM, and write Bend 2 graphics and math toward raylib parity.
- **Explore games and physics:** build a platformer and visual level editor, then investigate numerical methods and orbital motion through native and browser simulations.
- **Compare .NET approaches:** study REST/gRPC, EF Core/Dapper, authentication, observability, and Blazor UI behavior through executable examples.
- **Make projects easy to explore:** ship playable demos, Astro documentation, and CI checks that keep published claims aligned with the implementation.

---

### `$ ls ~/projects/active`

Public side projects and learning labs.

<table>
<tr><td>

**[csharpc](https://github.com/jonathanperis/csharpc)** \
A C# front-end for LLVM. It compiles C# to small native executables through Roslyn and LLVM, in the same family as clang, rustc, and gollvm. \
`C#` `Roslyn` `LLVM` `compilers` \
[Source](https://github.com/jonathanperis/csharpc)

</td></tr>
<tr><td>

**[jonlib](https://github.com/jonathanperis/jonlib)** \
Graphics and math libraries written in Bend 2, working toward raylib 6.0 parity, with differential tests against pinned raylib. \
`Bend 2` `raylib` `graphics` `math` \
[Source](https://github.com/jonathanperis/jonlib)

</td></tr>
<tr><td>

**[super-mango-editor](https://github.com/jonathanperis/super-mango-editor)** \
C11/raylib platformer, visual TOML level editor, and Sandbox School for learning game development. \
`C11` `raylib` `Emscripten` `WebAssembly` `level editor` `learning labs` \
[Play](https://www.jonathanperis.tech/super-mango-editor/) · [Learn](https://www.jonathanperis.tech/super-mango-editor/docs/learning-path/)

</td></tr>
<tr><td>

**[solar-system-simulator](https://github.com/jonathanperis/solar-system-simulator)** \
Physics-first orbital mechanics lab with a shared C core for native, WebAssembly, and headless runs; reproducible A/B experiments and a source-backed small-body atlas. \
`C11` `raylib` `WebAssembly` `numerical methods` `Verlet / Euler` `NASA / JPL data` \
[Simulate](https://www.jonathanperis.tech/solar-system-simulator/simulator/) · [Compare experiments](https://www.jonathanperis.tech/solar-system-simulator/compare/)

</td></tr>
<tr><td>

**[cpnucleo](https://github.com/jonathanperis/cpnucleo)** \
Hands-on .NET 10 project-management lab: compare REST/gRPC and EF Core/Dapper, explore architecture tradeoffs, and verify behavior with contract tests. \
`FastEndpoints` `PostgreSQL` `OpenTelemetry` `Astro` `TypeScript` `Docker` \
[Learning paths](https://www.jonathanperis.tech/cpnucleo/docs/learning-lab/)

</td></tr>
<tr><td>

**[blazor-mudblazor-starter](https://github.com/jonathanperis/blazor-mudblazor-starter)** \
Local-first .NET 10 learning sandbox for Blazor Server and MudBlazor: state, forms, APIs, persistence, authentication, localization, and CSV workflows. \
`Blazor Server` `MudBlazor` `EF Core` `SQLite` `Docker` `guided labs` \
[Learning guide](https://www.jonathanperis.tech/blazor-mudblazor-starter/docs/)

</td></tr>
<tr><td>

**[speedy-bird-lynx](https://github.com/jonathanperis/speedy-bird-lynx)** \
Flappy Bird-inspired arcade game exploring ReactLynx native UI: Android host, Lynx web preview, and a separate playable Canvas demo. iOS host source is a scaffold. \
`ReactLynx` `TypeScript` `Android` `Canvas` `Astro` \
[Play](https://www.jonathanperis.tech/speedy-bird-lynx/) · [Docs](https://www.jonathanperis.tech/speedy-bird-lynx/docs/)

</td></tr>
<tr><td>

**[jonathanperis.github.io](https://github.com/jonathanperis/jonathanperis.github.io)** \
Static portfolio and print-friendly resume, with build-time GitHub project data and a terminal-inspired UI. \
`Astro` `React` `TypeScript` `Tailwind CSS` `GitHub Pages` \
[Visit](https://www.jonathanperis.tech/) · [Resume](https://www.jonathanperis.tech/resume/)

</td></tr>
</table>

---

### `$ cat /proc/tech_stack`

```
+-------------------+----------------------------------------------------+
| Core              | C#, .NET, ASP.NET Core, Azure, SQL Server          |
| Architecture      | CQRS, DDD, Microservices, Clean Architecture       |
| Exploring         | Rust, Go, Python                                   |
| Backend           | .NET 10, FastEndpoints, REST/gRPC, EF Core, Dapper |
| Compilers         | C#, Roslyn, LLVM                                   |
| Games & physics   | C11, raylib, Emscripten, WebAssembly, Bend 2, TOML |
| Web & UI          | Astro, React, ReactLynx, TypeScript, Tailwind CSS  |
| .NET UI           | Blazor Server, MudBlazor                           |
| Data & delivery   | PostgreSQL, SQLite, Docker, GitHub Actions, Bun    |
| Observability     | OpenTelemetry                                      |
| Practice          | Learning labs, contract tests, reproducible runs   |
+-------------------+----------------------------------------------------+
```

---

### `$ neofetch`

```
   jonathan@itanhaem
   -----------------
   OS:        macOS / Linux / Docker
   Shell:     zsh + dotfiles
   Editor:    VS Code + JetBrains
   Uptime:    12+ years; .NET since May 2013
   Role:      Software Engineer, Derivative Path
   Loop:      build, inspect, measure, explain
   Packages:  NuGet, Bun, Cargo, pip
   Theme:     Dark Terminal Aesthetic

   Contact:   jperis.silva@gmail.com
   Portfolio: https://www.jonathanperis.tech/
   Twitter:   @jperis_silva
```

---

<p align="center">
  <b><a href="https://www.jonathanperis.tech/">Live demo →</a></b> | <b><a href="https://github.com/jonathanperis/jonathanperis/wiki">Documentation →</a></b>
</p>

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake.svg" />
  <img alt="github-snake" src="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake-dark.svg" width="100%" />
</picture>

---

<p align="center">
  <sub>hint: visit <a href="https://www.jonathanperis.tech/">jonathanperis.tech</a> and try the Konami code</sub>
</p>
