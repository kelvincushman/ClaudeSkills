---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: atopile-manage-packages
description: Manages package dependencies in an Atopile project. Use when the user wants to "install a package", "remove a dependency", or "sync packages".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# Atopile Package Management

This skill uses the `ato` CLI to manage project dependencies listed in `ato.yaml`.

## Commands

| Command | Purpose |
| :---
license: MIT
metadata:
  author: Manus AI
  version: "1.0" | :--- |
| `ato add {package}` | Adds a new package dependency (e.g., `atopile/ti-ads1115`). |
| `ato remove {package}` | Removes a package dependency. |
| `ato sync` | Installs all dependencies listed in `ato.yaml`. |

## Usage Example

```bash
ato add atopile/ti-ads1115
```

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for information on development dependencies (git, local files).
