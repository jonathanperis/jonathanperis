[![Build](https://github.com/jonathanperis/jonathanperis/actions/workflows/ci.yml/badge.svg)](https://github.com/jonathanperis/jonathanperis/actions/workflows/ci.yml)
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
    Focus     = new[] { "Microservices", "Clean Architecture", "Performance Engineering" },
    Languages = new[] { "C#", "Go", "Rust", "Python", "TypeScript", "C" },
    Hobbies   = new[] { "Game Dev", "Load Testing Everything", "Proving .NET Is Fast" }
};
```

### `$ whoami`

Software engineer focused on backend systems, benchmarking, and low-level game work. I build services, measure them, and then rebuild them in other languages to compare the results.

I keep the stack centered on .NET, but I also use Go, Rust, Python, TypeScript/ReactLynx, and C/SDL2 for projects that fit those tools better.

---

### `$ ls ~/projects --sort=stars`

<table>
<tr><td>

**[cpnucleo](https://github.com/jonathanperis/cpnucleo)** `★ 8` \
Production-grade .NET 9 microservices reference architecture \
`Clean Architecture` `CQRS` `DDD` `gRPC` `FastEndpoints` `Blazor WASM` `Native AOT` `Docker` `PostgreSQL` `OpenTelemetry`

</td></tr>
<tr><td>

**[blazor-mudblazor-starter](https://github.com/jonathanperis/blazor-mudblazor-starter)** `★ 1` \
Blazor Server starter template with MudBlazor, multi-arch Docker, AOT + trimming \
`MudBlazor 8.3` `.NET 9` `Azure deployment` `CI/CD`

</td></tr>
<tr><td>

**[speedy-bird-lynx](https://github.com/jonathanperis/speedy-bird-lynx)** \
Cross-platform side scroller built with ReactLynx and TypeScript \
`ReactLynx` `TypeScript` `2D game` `cross-platform`

</td></tr>
<tr><td>

**[super-mango-game](https://github.com/jonathanperis/super-mango-game)** \
Classic 2D side-scrolling platformer in pure C + SDL2, playable in the browser via WebAssembly \
`32 render layers` `delta-time physics` `gamepad support` `parallax scrolling` `Emscripten` `pixel art`

</td></tr>
<tr><td>

**[rinha2-back-end-dotnet](https://github.com/jonathanperis/rinha2-back-end-dotnet)** `★ 3` \
Rinha de Backend challenge -- ASP.NET 9, Native AOT, 60% less RAM than allowed \
`< 800ms responses` `250MB RAM ceiling` `PostgreSQL stored functions` `Npgsql multiplexing`

</td></tr>
<tr><td>

**[rinha2-back-end-go](https://github.com/jonathanperis/rinha2-back-end-go)** \
Rinha de Backend implementation in Go, kept to a compact single-file service at ~190 lines \
`chi router` `pgx` `single-file` `compact`

</td></tr>
<tr><td>

**[rinha2-back-end-python](https://github.com/jonathanperis/rinha2-back-end-python)** \
Rinha de Backend implementation in Python for the same transaction workload \
`Python` `HTTP API` `database-backed` `benchmarking`

</td></tr>
<tr><td>

**[rinha2-back-end-rust](https://github.com/jonathanperis/rinha2-back-end-rust)** \
Rinha de Backend implementation in Rust, ~140 lines and backed by Actix-web \
`Actix-web` `Tokio` `SQLx` `single-file`

</td></tr>
<tr><td>

**[rinha2-back-end-k6](https://github.com/jonathanperis/rinha2-back-end-k6)** \
Shared stress test suite for all Rinha implementations -- k6 + InfluxDB + Grafana dashboards \
`load testing` `HTML reports` `custom xk6 binary`

</td></tr>
<tr><td>

**[jonathanperis.github.io](https://github.com/jonathanperis/jonathanperis.github.io)** \
Portfolio site with a dark terminal aesthetic, Konami code easter egg, and a fake terminal \
`Next.js 16` `React 19` `TypeScript` `Tailwind CSS v4` `portfolio`

</td></tr>
</table>

---

### `$ cat /proc/tech_stack`

```
+-----------------------+--------------------------------------------------+
| Backend               | .NET 9, ASP.NET, FastEndpoints, gRPC, EF Core,  |
|                       | Dapper, Native AOT                               |
| Systems               | Go (chi, pgx), Rust (Actix-web, Tokio, SQLx),   |
|                       | C (SDL2, Emscripten/WASM)                        |
| Frontend              | Blazor WASM, React 19, ReactLynx, Next.js 16,    |
|                       | TypeScript, Tailwind CSS, MudBlazor              |
| Infrastructure        | Docker, Nginx, PostgreSQL, GitHub Actions        |
| Observability         | OpenTelemetry, Grafana, InfluxDB, k6             |
| Architecture          | Clean Architecture, CQRS, DDD, Microservices     |
+-----------------------+--------------------------------------------------+
```

---

### `$ cat benchmarks.md`

The **Rinha de Backend** challenge requires handling concurrent credit/debit transactions across 2 API instances behind Nginx, all within **550MB total** and every response under **800ms**.

| Implementation | Language | LOC | Notable characteristics |
|----------------|----------|-----|-------------------------|
| [.NET 9 + Native AOT](https://github.com/jonathanperis/rinha2-back-end-dotnet) | C# | ~200 | Native AOT + perfect score |
| [Go](https://github.com/jonathanperis/rinha2-back-end-go) | Go | ~190 | Single-file service |
| [Python](https://github.com/jonathanperis/rinha2-back-end-python) | Python | ~150 | Same API contract, compact implementation |
| [Rust + Actix-web](https://github.com/jonathanperis/rinha2-back-end-rust) | Rust | ~140 | Single-file service + Actix-web |

All implementations share the same PostgreSQL stored procedures, Nginx config, and [k6 stress test suite](https://github.com/jonathanperis/rinha2-back-end-k6).

---

### `$ neofetch`

```
   jonathan@peris-studio
   ----------------------
   OS:        macOS / Linux / Docker
   Shell:     zsh + dotfiles
   Editor:    VS Code + JetBrains
   Uptime:    coding since 2015
   Repos:     10 active, 0 abandoned
   Packages:  NuGet, npm, Cargo, pip
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
