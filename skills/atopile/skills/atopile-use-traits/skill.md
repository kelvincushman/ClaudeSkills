---
name: atopile-use-traits
description: Applies advanced traits like bridging and shared references to extend module functionality. Use when simplifying connections across modules or sharing power rails.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Traits

Traits are powerful extensions that automate common connection patterns within and across modules.

## Supported Traits

- **can_bridge_by_name**: Enables the "sperm operator" (`~>`) for daisy-chaining modules.
- **has_single_electric_reference_shared**: Automatically connects all internal signal references to a common power rail.

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for trait parameters and experiment flags.
- See [usage examples](examples/examples.md) for bridging and shared reference patterns.
