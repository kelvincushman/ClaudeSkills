# Atopile Language Reference

## Built-in Types
- `Electrical`: A single electrical node.
- `ElectricSignal`: A signal with a reference (usually GND).
- `ElectricPower`: A power interface with `hv` and `lv`.

## Inheritance
Modules can inherit from other modules using the `from` keyword.
```ato
module SubModule from BaseModule:
    # Override or add properties
```

## Units and Tolerances
- **Resistance**: `ohm`, `kohm`, `Mohm`
- **Capacitance**: `uF`, `nF`, `pF`
- **Voltage**: `V`, `mV`
- **Tolerances**: `10kohm +/- 1%`, `3.3V to 3.6V`
