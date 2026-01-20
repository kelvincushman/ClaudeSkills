# Atopile Traits Reference

## `can_bridge_by_name` Trait

This trait enables the "sperm operator" (`~>`) for bridging connections over a module.

| Parameter | Default | Description |
| :--- | :--- | :--- |
| `input_name` | `"input"` | The name of the input interface to bridge from. |
| `output_name` | `"output"` | The name of the output interface to bridge to. |

**Required Pragmas**:
```atopile
#pragma experiment("MODULE_TEMPLATING")
#pragma experiment("BRIDGE_CONNECT")
#pragma experiment("TRAITS")
import can_bridge_by_name
```

## `has_single_electric_reference_shared` Trait

This trait simplifies connecting all electric references (grounds) within a module.

| Parameter | Default | Description |
| :--- | :--- | :--- |
| `gnd_only` | `false` | If `true`, only the low-voltage reference (`lv`) is connected. |

**Required Pragmas**:
```atopile
#pragma experiment("MODULE_TEMPLATING")
#pragma experiment("TRAITS")
import has_single_electric_reference_shared
```
