---
name: atopile-manage-packages
description: Manages Atopile package dependencies. Use when adding new libraries, removing unused packages, or synchronizing the local environment with the registry.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Package Management

This skill guides you through managing external dependencies in your Atopile project.

## Basic Commands

- **Add**: `ato install <package_name>`
- **Remove**: `ato uninstall <package_name>`
- **Sync**: `ato install` (installs all packages listed in `ato.yaml`)

## Package Storage
Dependencies are installed into the `.ato/modules/` directory. This directory should typically be ignored by Git.

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for `ato.yaml` dependency syntax and registry details.
- See [usage examples](examples/examples.md) for common package management workflows.
