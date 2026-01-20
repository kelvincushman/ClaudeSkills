# Atopile Assertion Examples

## Voltage Divider Solver
```ato
module MyDivider:
    v_in = 5V +/- 1%
    v_out: voltage
    r_top = new Resistor
    r_bottom = new Resistor
    
    assert v_out is v_in * r_bottom.resistance / (r_top.resistance + r_bottom.resistance)
    assert v_out within 3.3V +/- 5%
```

## Power Budget Check
```ato
module System:
    total_current: current
    assert total_current is sensor.current + mcu.current
    assert total_current < 500mA
```
