# Performance Engineering

> How the current projects measure behavior instead of arguing about it

## Philosophy

The public projects treat performance as something you can rerun:

1. **Measure a real program** -- simulators, games, and compilers
2. **Keep the experiment repeatable** -- same inputs, a recorded method, and a result someone else can check
3. **Change one thing at a time** -- numerical method, runtime, or architecture, then compare
4. **Leave the evidence next to the code** -- docs and labs ship with the repository

## Where that shows up

### solar-system-simulator

A shared C core runs natively, in WebAssembly, and headless. Reproducible A/B experiments compare numerical methods on the same orbital problem, with a source-backed small-body atlas beside the simulation.

### csharpc

A C# front-end for LLVM. It compiles C# to small native executables through Roslyn and LLVM, the same kind of job clang, rustc, and gollvm do for their languages.

### cpnucleo

The .NET lab compares REST with gRPC and EF Core with Dapper. Contract tests and OpenTelemetry make the tradeoff visible in a running system.

### super-mango-editor and speedy-bird-lynx

Both ship something you can run. The platformer plays in the browser through WebAssembly. The arcade game has a browser demo and an Android host. The source and the playable build stay together.

## Observability

cpnucleo records traces and metrics with OpenTelemetry, so request and database time can be inspected while comparing API and data-access choices.
