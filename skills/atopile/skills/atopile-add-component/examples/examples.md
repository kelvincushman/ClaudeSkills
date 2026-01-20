# Atopile Component Examples

## Forcing a Specific LCSC Part
```ato
import Capacitor
cap = new Capacitor
cap.lcsc_id = "C11702"  # Forces a specific 100nF 0402 cap
```

## Defining a Custom Component
```ato
component MyIC:
    package = "QFN-16_3x3mm_P0.5mm"
    mpn = "TPS62130RGTR"
    pin 1 ~ gnd
```
