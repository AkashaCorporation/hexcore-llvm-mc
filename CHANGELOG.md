# Changelog

All notable changes to `hexcore-llvm-mc` will be documented in this file.

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
