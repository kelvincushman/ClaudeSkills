---
name: atopile-build-project
description: Compiles Atopile projects to generate netlists, update PCB layouts, and produce manufacturing data. Use when validating the design, updating KiCAD, or preparing for production.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Build and Compilation

This skill guides you through the build process, from compiling `.ato` code to updating your KiCAD layout.

## Basic Commands

- **Build**: `ato build`
- **Verbose Build**: `ato -v build`
- **Specific Target**: `ato build --target <target_name>`

## Build Artifacts
The build process generates files in the `build/` directory, including:
- Netlists
- BOM (Bill of Materials)
- Manufacturing data (Gerbers, etc.)

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for build process details and CLI options.
- See [usage examples](examples/examples.md) for common build workflows.
