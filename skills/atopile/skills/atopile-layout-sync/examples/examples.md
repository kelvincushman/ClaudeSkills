# Atopile Layout Examples

## Reusing a Package Layout
```ato
from "rp2040/RP2040Kit.ato" import RP2040Kit
module App:
    uc = new RP2040Kit
```
1. Run `ato build`.
2. In KiCAD, select the `uc` group.
3. Use the Atopile plugin to "Pull" the layout.
