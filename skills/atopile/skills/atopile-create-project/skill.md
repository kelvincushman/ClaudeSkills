---
name: atopile-create-project
description: Initializes a new Atopile project from a template. Use when starting a new hardware design or creating a fresh workspace.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Project Creation

This skill guides you through initializing a new Atopile project.

## Basic Command

```bash
ato create project <project_name>
```

## Project Structure
A new project includes:
- `ato.yaml`: Project configuration.
- `src/`: Source code directory (`.ato` files).
- `layouts/`: KiCAD layout files.

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for `ato.yaml` configuration and project organization.
- See [usage examples](examples/examples.md) for initializing and first build.
