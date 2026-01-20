---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: atopile-build-project
description: Compiles the Atopile project, updates the PCB layout, and generates manufacturing data. Use when the user wants to "build the circuit", "compile the design", or "generate gerbers".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# Atopile Project Build

This skill executes the core build process of an Atopile project.

## Usage

```bash
ato build
```

## Options

| Option | Purpose |
| :---
license: MIT
metadata:
  author: Manus AI
  version: "1.0" | :--- |
| `--open` | Opens the generated KiCAD file after a successful build. |
| `-v`, `-vv`, `-vvv` | Increases the verbosity of the compiler output. |
| `--debug` | Runs the compiler in debug mode on port `5678`. |

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for the full build process steps and output artifacts.
