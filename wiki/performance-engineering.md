# Performance Engineering

> Benchmarking philosophy, optimization techniques, and stress testing methodology

## Philosophy

Jonathan's approach to performance is empirical, not speculative:

1. **Measure first** -- never optimize without a baseline
2. **Same spec, different implementations** -- compare languages fairly by using identical infrastructure
3. **Real constraints** -- work within the challenge's memory and latency budgets, not arbitrary ones
4. **Shared test suite** -- one k6 test suite tests all implementations, ensuring apples-to-apples comparison

## The Rinha de Backend Constraints

| Resource | Budget |
|----------|--------|
| Total RAM | 550MB (2 API instances + PostgreSQL + Nginx) |
| Response time | < 800ms per request |
| Concurrency | Multiple simultaneous clients |
| Consistency | ACID transactions for credit/debit operations |

## Optimization Techniques by Language

### C# / .NET 9

The most aggressively optimized implementation -- uses **60% less RAM** than the allowed budget.

| Technique | Impact |
|-----------|--------|
| **Native AOT** | Eliminates JIT compilation, reduces startup to milliseconds |
| **Trimming** | Removes unused code, shrinking the binary |
| **Source generators** | System.Text.Json generates serialization code at compile time -- zero reflection |
| **Npgsql multiplexing** | Multiple SQL queries share fewer TCP connections to PostgreSQL |
| **Connection pooling** | Pre-warmed database connections ready for requests |
| **Stored functions** | Business logic in PostgreSQL -- one round trip per request |

### Rust (Actix-web + Tokio)

Naturally memory-efficient due to zero-cost abstractions:
- **Actix-web** -- one of the fastest HTTP frameworks in any language
- **Tokio** -- async runtime with work-stealing scheduler
- **SQLx** -- compile-time verified SQL queries (catches errors before runtime)
- **No GC** -- deterministic memory management

### Go (chi + pgx)

Go's simplicity works in its favor:
- **chi/v5** -- lightweight router, minimal overhead
- **pgx/v5** -- low-level PostgreSQL driver (more efficient than database/sql)
- **Goroutines** -- lightweight concurrency without thread-per-request overhead
- **Static binary** -- single binary deployment, no runtime dependencies

### Python

The underdog that still meets the budget:
- **Stored procedures** do the heavy lifting -- Python is just the HTTP layer
- Demonstrates that language speed matters less when the database is doing the real work

## Stress Testing with k6

The [rinha2-back-end-k6L(https://github.com/jonathanperis/rinha2-back-end-k6.md) project provides the shared test infrastructure.

### Architecture

```
k6 (custom binary with xk6-output-influxdb)
    |
    +---> API (Nginx -> API Instance 1 + API Instance 2)
    |
    +---> InfluxDB (metrics export, dev mode)
    |
    +---> HTML Report (standalone, prod mode)
```

### Two Modes

**Dev Mode** -- Real-time Observability
- k6 exports metrics to InfluxDB
- Grafana dashboards show request rates, latencies, error rates in real time
- Useful for identifying bottlenecks during development

**Prod Mode** -- Standalone Reports
- k6 generates HTML reports
- No external dependencies needed
- Reports deployed to GitHub repos for public visibility

### Custom k6 Binary

The test suite uses a custom-built k6 binary compiled with Go, including the `xk6-output-influxdb` extension. This is Dockerized so the full test infrastructure runs with a single `docker compose up`.

## Observability Stack

### OpenTelemetry (cpnucleo, rinha2-dotnet)

Distributed tracing and metrics collection integrated at the application level:
- Request tracing across service boundaries
- Database query timing
- Custom business metrics

### Grafana + InfluxDB (rinha2-k6)

Time-series visualization for stress test metrics:
- Requests per second
- Response time percentiles (p50, p95, p99)
- Error rates
- Virtual user counts

## Key Takeaways

1. **PostgreSQL stored functions are the great equalizer** -- when the database does the work, the application language matters less than you'd think
2. **.NET Native AOT is competitive with Rust and Go** for this class of workload -- the 60% RAM savings in the C# implementation proves it
3. **Shared infrastructure eliminates excuses** -- same Docker Compose, same Nginx config, same database schema means the only variable is the application code
4. **Always test under realistic constraints** -- the Rinha challenge's 550MB budget forces real optimization, not just theoretical benchmarks
