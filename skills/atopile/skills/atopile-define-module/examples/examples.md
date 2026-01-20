# Atopile Module Examples

## Simple Voltage Divider
```ato
import Resistor, ElectricPower, ElectricSignal

module VoltageDivider:
    power = new ElectricPower
    output = new ElectricSignal
    r_top = new Resistor
    r_bottom = new Resistor

    power.hv ~ r_top.p1; r_top.p2 ~ output.line
    output.line ~ r_bottom.p1; r_bottom.p2 ~ power.lv
```

## Component with Specific Part
```ato
component LDO:
    mpn = "TLV70233DBVR"
    package = "SOT-23-5"
    v_in = new ElectricPower
    v_out = new ElectricPower
```
