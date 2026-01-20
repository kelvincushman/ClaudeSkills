# Atopile Traits Reference

## Experiment Flags
Traits currently require specific experiment pragmas:
```ato
#pragma experiment("MODULE_TEMPLATING")
#pragma experiment("BRIDGE_CONNECT")
#pragma experiment("TRAITS")
```

## Trait Details
### `can_bridge_by_name`
- **Parameters**: `input_name` (default: "input"), `output_name` (default: "output").
- **Usage**: Allows `signal_in ~> module_a ~> module_b ~> signal_out`.

### `has_single_electric_reference_shared`
- **Parameters**: `gnd_only` (default: false).
- **Usage**: Connects all `ElectricSignal.reference` to the module's `ElectricPower`.
