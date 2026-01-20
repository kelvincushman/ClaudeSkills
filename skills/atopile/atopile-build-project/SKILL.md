---
name: atopile-build-project
description: Compiles the Atopile project, updates the PCB layout, and generates manufacturing data. Use when the user wants to "build the circuit", "compile the design", or "generate gerbers".
---

# Atopile Project Build

This skill executes the core build process of an Atopile project.

## Usage

```bash
ato build
```

## Options

| Option | Purpose |
| :--- | :--- |
| `--open` | Opens the generated KiCAD file after a successful build. |
| `-v`, `-vv`, `-vvv` | Increases the verbosity of the compiler output. |
| `--debug` | Runs the compiler in debug mode on port `5678`. |

## Reference

See [reference.md](reference.md) for the full build process steps and output artifacts.
