# Unsafe Rust Benchmarks and Analysis Suite

This project provides a benchmark suite and a dynamic analysis suite for unsafe Rust, accompanying *Dynamic Analysis of Unsafe Rust: Behaviors and Benchmarks*. The benchmarks support evaluating the performance and memory overhead of security defenses for unsafe Rust. The analysis suite reports CPU cycles spent in unsafe code, heap objects and memory accessed by unsafe code, executed unsafe instruction counts and types, and execution frequencies of functions containing unsafe code. Measurements can include or exclude attribution of unsafe code incorporated from Rust’s standard libraries.

## Repositories

| Repository | Contents |
| --- | --- |
| [Rust compiler](https://github.com/GWSysSec/unsafe-rust-benchmark) | Modified `rustc` that preserves unsafe-code metadata through compilation, enabling analysis at the LLVM IR level. |
| [LLVM](https://github.com/GWSysSec/unsafe-llvm-benchmark) | Modified LLVM backend with instrumentation passes for CPU cycles, heap accesses, and instruction and function execution counts. Included as a submodule of the Rust compiler repository. |
| [Benchmarks](https://github.com/GWSysSec/rust-unsafe-benchmark) | Benchmark suite for evaluating defenses against unsafe Rust. See its README for benchmark descriptions, configurations, and execution instructions. |
| [Artifacts](https://github.com/GWSysSec/unsaferust-benchmark-artifact) | Packaged toolchain, instrumentation runtime, experimental workloads, measurement data, and scripts for reproducing the experiments. See its README to get started. |

## Compiler Layout

The LLVM repository is nested inside the Rust compiler repository as the `src/llvm-project` Git submodule:

```text
unsafe-rust-benchmark/          # Rust compiler repository
└── src/
    └── llvm-project/          # unsafe-llvm-benchmark submodule
```

