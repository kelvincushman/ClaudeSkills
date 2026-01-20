---
name: atopile-layout-sync
description: Synchronizes Atopile code changes with the KiCAD PCB layout. Use when updating component placements, net names, or reusing layouts from existing modules.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Layout Synchronization

This skill guides you through the process of keeping your KiCAD PCB layout in sync with your Atopile code.

## Core Workflow

1.  **Build**: Run `ato build` to update the netlist and KiCAD project.
2.  **KiCAD Plugin**: Use the Atopile KiCAD plugin to sync groups and components.
3.  **Sync Group**: Hit the "Sync Group" button in KiCAD to pull layout data from reusable modules.

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for plugin installation and layout reuse rules.
- See [usage examples](examples/examples.md) for common layout sync scenarios.
