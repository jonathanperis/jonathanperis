# Rinha de Backend

> The same API challenge implemented in 4 languages, stress tested to the limit

## Overview

The **Rinha de Backend** ("Backend Fight") is a Brazilian programming challenge that tests how well developers can build high-performance APIs under strict resource constraints. Jonathan has implemented the challenge in **four different languages**, sharing the same PostgreSQL schema, Nginx configuration, and k6 stress test suite across all of them.

This is polyglot engineering at its most honest: same spec, same infrastructure, same benchmarks -- only the application code changes.

## The Challenge

Manage fictional bank clients with credit and debit transactions. Requirements:
- **2 API instances** behind an Nginx load balancer
- **Total memory budget**: 550MB (for everything -- API instances, database, proxy)
- **Every response** must complete in under **800ms**
- Handle concurrent transactions with proper consistency

## Implementations

### C# / .NET 9 -- [rinha2-back-end-dotnetL(https://github.com/jonathanperis/rinha2-back-end-dotnet.md)

The most optimized implementation. Key techniques:
- **Native AOT** compilation -- no JIT, minimal startup time
- **Trimming** -- dead code elimination for smaller binaries
- **Npgsql connection pooling with multiplexing** -- multiple queries over fewer TCP connections
- **System.Text.Json source generators** -- zero-reflection JSON serialization
- **PostgreSQL stored functions** -- push logic to the database to minimize round trips
- **Result**: uses **60% less RAM** than the allowed budget

**Stars**: 3 | **LOC**: ~200 | **Languages**: C# (7,308B), PLpgSQL (8,408B), HTML (170,892B for reports)

### Rust -- [rinha2-back-end-rustL(https://github.com/jonathanperis/rinha2-back-end-rust.md)

Minimal and elegant:
- **Actix-web 4** -- high-performance HTTP framework
- **SQLx 0.7** -- compile-time checked SQL queries
- **Tokio** -- async runtime
- **Single-file API** in ~140 lines

**Languages**: Rust (4,650B), PLpgSQL (8,408B)

### Go -- [rinha2-back-end-goL(https://github.com/jonathanperis/rinha2-back-end-go.md)

Idiomatic Go approach:
- **Go 1.23**
- **chi/v5** -- lightweight router
- **pgx/v5** -- PostgreSQL driver with connection pooling
- **Single-file API** in ~190 lines

**Stars**: 1 | **Languages**: Go (5,411B), PLpgSQL (8,408B)

### Python -- [rinha2-back-end-pythonL(https://github.com/jonathanperis/rinha2-back-end-python.md)

Proving Python can compete:
- Same architecture with 2 API instances
- PostgreSQL stored procedures handle the heavy lifting
- ~150 lines of application code

**Languages**: Python (4,837B), PLpgSQL (8,408B)

## Shared Infrastructure

All four implementations share:
- **PostgreSQL stored procedures** (identical `PLpgSQL` across all repos)
- **Nginx reverse proxy** configuration (round-robin between 2 instances)
- **Docker Compose** orchestration
- **k6 stress test suite** ([rinha2-back-end-k6L(https://github.com/jonathanperis/rinha2-back-end-k6.md))

## Stress Testing -- rinha2-back-end-k6

The [k6 test suiteL(https://github.com/jonathanperis/rinha2-back-end-k6.md) is its own project:
- **Custom k6 binary** built with Go (xk6-output-influxdb extension)
- **Dev mode**: exports metrics to InfluxDB for Grafana dashboards in real time
- **Prod mode**: generates standalone HTML reports
- **Dockerized**: run the full test infrastructure with one command

**Languages**: JavaScript (11,140B), Shell (521B)

## Key Insight

The PostgreSQL stored functions do the heavy lifting in all implementations. The application layer is thin by design -- it validates input, calls the stored procedure, and returns the result. This is why all implementations can be so small (140-200 LOC): the real logic lives in the database, where it belongs for this workload.

The .NET implementation's 60% RAM savings come from Native AOT and aggressive trimming, not from algorithmic differences. The Rust implementation is naturally memory-efficient. Go and Python fall within budget comfortably.
