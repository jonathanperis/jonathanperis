```
> "A Vinganca nunca e plena, mata a alma e a envenena." - Seu Madruga
```

```csharp
var jonathan = new Developer
{
    Location  = "Itanhaem, SP, Brazil",
    Company   = "Peris Studio",
    Focus     = new[] { "Microservices", "Clean Architecture", "Performance Engineering" },
    Languages = new[] { "C#", "Rust", "Go", "C", "Python", "TypeScript" },
    Hobbies   = new[] { "Game Dev", "Load Testing Everything", "Proving .NET Is Fast" }
};
```

### `$ whoami`

Software engineer who builds production-grade backend systems by day and retro 2D platformers by night. I don't just write services -- I benchmark them, stress test them, then rewrite them in another language to see if it's faster. Spoiler: .NET with Native AOT usually wins.

I believe the best way to understand a technology is to push it to its limits. That's why I implemented the same API challenge in **four languages** and obsessively measured every microsecond.

---

### `$ ls ~/projects --sort=stars`

<table>
<tr><td>

**[cpnucleo](https://github.com/jonathanperis/cpnucleo)** `★ 8` \
Production-grade .NET 9 microservices reference architecture \
`Clean Architecture` `CQRS` `DDD` `gRPC` `FastEndpoints` `Blazor WASM` `Native AOT` `Docker` `PostgreSQL` `OpenTelemetry`

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

**[rinha2-back-end-rust](https://github.com/jonathanperis/rinha2-back-end-rust)** | **[go](https://github.com/jonathanperis/rinha2-back-end-go)** `★ 1` | **[python](https://github.com/jonathanperis/rinha2-back-end-python)** \
Same challenge. Same constraints. Three more languages. ~140-190 lines each. \
`Actix-web` `chi router` `pgx` `SQLx` `Tokio`

</td></tr>
<tr><td>

**[rinha2-back-end-k6](https://github.com/jonathanperis/rinha2-back-end-k6)** \
Shared stress test suite for all Rinha implementations -- k6 + InfluxDB + Grafana dashboards \
`load testing` `HTML reports` `custom xk6 binary`

</td></tr>
<tr><td>

**[jonathanperis.github.io](https://github.com/jonathanperis/jonathanperis.github.io)** \
Portfolio site with a dark terminal aesthetic, Konami code easter egg, and a fake terminal \
`Next.js 16` `React 19` `TypeScript` `Tailwind CSS v4` `try: sudo hire me`

</td></tr>
<tr><td>

**[blazor-mudblazor-starter](https://github.com/jonathanperis/blazor-mudblazor-starter)** `★ 1` \
Blazor Server starter template with MudBlazor, multi-arch Docker, AOT + trimming \
`MudBlazor 8.3` `.NET 9` `Azure deployment` `CI/CD`

</td></tr>
</table>

---

### `$ cat /proc/tech_stack`

```
+-----------------------+--------------------------------------------------+
| Backend               | .NET 9, ASP.NET, FastEndpoints, gRPC, EF Core,  |
|                       | Dapper, Native AOT                               |
| Systems               | Rust (Actix-web, Tokio, SQLx), Go (chi, pgx),   |
|                       | C (SDL2, Emscripten/WASM)                        |
| Frontend              | Blazor WASM, React 19, Next.js 16, TypeScript,   |
|                       | Tailwind CSS, MudBlazor                          |
| Infrastructure        | Docker, Nginx, PostgreSQL, GitHub Actions         |
| Observability         | OpenTelemetry, Grafana, InfluxDB, k6             |
| Architecture          | Clean Architecture, CQRS, DDD, Microservices     |
+-----------------------+--------------------------------------------------+
```

---

### `$ cat benchmarks.md`

The **Rinha de Backend** challenge requires handling concurrent credit/debit transactions across 2 API instances behind Nginx, all within **550MB total** and every response under **800ms**.

| Implementation | Language | LOC  | RAM Usage vs Limit |
|----------------|----------|------|--------------------|
| [.NET 9 + Native AOT](https://github.com/jonathanperis/rinha2-back-end-dotnet) | C# | ~200 | **60% less** than allowed |
| [Actix-web 4](https://github.com/jonathanperis/rinha2-back-end-rust) | Rust | ~140 | well under limit |
| [chi/v5 + pgx](https://github.com/jonathanperis/rinha2-back-end-go) | Go | ~190 | well under limit |
| [Python](https://github.com/jonathanperis/rinha2-back-end-python) | Python | ~150 | within limit |

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
   Portfolio: jonathanperis.github.io
   Twitter:   @jperis_silva
```

---

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake.svg" />
  <img alt="github-snake" src="https://raw.githubusercontent.com/jonathanperis/jonathanperis/output/github-contribution-grid-snake-dark.svg" width="100%" />
</picture>

---

<p align="center">
  <sub>hint: visit <a href="https://jonathanperis.github.io">jonathanperis.github.io</a> and try the Konami code</sub>
</p>
