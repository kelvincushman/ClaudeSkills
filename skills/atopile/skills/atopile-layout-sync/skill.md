---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: atopile-layout-sync
description: Synchronizes the Atopile design with the KiCAD layout file. Use when the user wants to "sync layout", "pull layout from package", or "install KiCAD plugin".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# Atopile Layout Synchronization

This skill manages the interaction between the Atopile code and the KiCAD layout.

## Key Actions

1.  **Open KiCAD**: Run `ato build` (or `ato build --open`) to generate and open the KiCAD project file.
2.  **Install Plugin**: Run `ato configure` to ensure the Atopile KiCAD plugin is installed.
3.  **Sync Layout**: Use the "Sync Group" and "Pull" buttons in the KiCAD plugin to reuse layouts from imported packages.

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for details on creating reusable layouts for custom modules.
