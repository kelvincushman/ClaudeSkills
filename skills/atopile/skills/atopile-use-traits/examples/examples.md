# Atopile Trait Examples

## Bridging Logic Signals
```ato
module Buffer:
    input = new ElectricLogic
    output = new ElectricLogic
    trait can_bridge_by_name

module App:
    sig_in ~> buf1 ~> buf2 ~> sig_out
```

## Shared Ground Reference
```ato
module SensorBlock:
    data = new ElectricLogic
    clock = new ElectricLogic
    power = new ElectricPower
    # Connects data.reference.lv and clock.reference.lv to power.lv
    trait has_single_electric_reference_shared<gnd_only=true>
```
