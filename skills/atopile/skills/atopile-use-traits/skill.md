---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: atopile-use-traits
description: Applies traits to Atopile modules to extend functionality, such as bridging connections or sharing electric references. Use when the user wants to "use a trait", "bridge a module", or "share ground references".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# Atopile Trait Application

Traits are used to extend the functionality of a module.

## Supported Traits

| Trait | Purpose |
| :---
license: MIT
metadata:
  author: Manus AI
  version: "1.0" | :--- |
| `can_bridge_by_name` | Enables the `~>` operator for bridging connections over a module. |
| `has_single_electric_reference_shared` | Connects all electric references (grounds) within the module together. |

## Usage Example (`can_bridge_by_name`)

```atopile
module BridgableModule:
    input = new ElectricLogic
    output = new ElectricLogic
    trait can_bridge_by_name<input_name="input", output_name="output">
```

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for import pragmas and detailed trait parameters.
