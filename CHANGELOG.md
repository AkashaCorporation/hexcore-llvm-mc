# Changelog

All notable changes to `hexcore-llvm-mc` will be documented in this file.

## [1.0.1] - 2026-03-19

### Fixed

- **`assembleMultiple()` stability** — replaced the aggressive parser/streamer reuse path with a safer per-instruction assembly flow built on `AssembleCode(...)`. This prevents the process exits and instability observed when assembling instruction arrays in real HexCore patch/export workflows.
- **Per-instruction result trust** — `assembleMultiple()` now resolves each instruction independently and advances `currentAddress` using the actual emitted byte length for the previous instruction, improving predictability of returned `size` and `bytes`.
- **Error reporting for batch assembly** — failures in `assembleMultiple()` now report the failing instruction index together with the underlying assembly error, making it much easier to diagnose problematic statements in headless and interactive workflows.

### Notes

- This release prioritizes correctness and survivability over the previous pipeline-reuse optimization strategy.
- The change was validated against the monorepo `Wave 1` integration work where `assembleMultiple()` stability is part of the LLVM-MC wrapper hardening effort.

## [1.0.0] - 2026-02-14

### Added

- Published to npm.
- Prebuild loader tries both underscore and hyphen naming conventions.

### Fixed

- **`.vscodeignore`** — added `!prebuilds/**` force-include for packaged builds.

## [0.9.0] - 2026-02-01

### Added

- Initial release.
- LLVM 18.1.8 MC-based assembler N-API bindings.
- Multi-architecture support: X86, ARM, ARM64, MIPS, RISC-V, PowerPC, SPARC, SystemZ, Hexagon, WebAssembly, BPF, LoongArch.
- Synchronous and asynchronous assembly.
- Intel and AT&T syntax support for x86.
- CPU-specific code generation with feature flags.
- TypeScript definitions included.
