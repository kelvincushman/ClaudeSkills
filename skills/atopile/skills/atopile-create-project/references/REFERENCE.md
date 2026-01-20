# Atopile Project Reference

## `ato.yaml` Overview
The `ato.yaml` file defines:
- **Project Name**: The unique name of the project.
- **Entry Point**: The main `.ato` file and module to build.
- **Build Targets**: Different configurations (e.g., PCBA, Test Jig).
- **Dependencies**: External packages required.

## Directory Layout
- `src/main.ato`: Default entry point.
- `.ato/`: Internal cache and dependencies (ignore in Git).
- `build/`: Output artifacts (ignore in Git).
