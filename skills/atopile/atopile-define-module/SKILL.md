---
name: atopile-define-module
description: Defines a new module or component in the Atopile language, including interfaces, connections, and constraints. Use when the user wants to "create a new module", "define a voltage divider", or "subclass a component".
---

# Atopile Module Definition

This skill guides the creation of new `module` or `component` blocks in the `.ato` language.

## Core Concepts

*   **Types**: `module`, `interface`, `component`.
*   **Subclassing**: `module SubclassedModule from SomeModule:`
*   **Connections**: Use the `~` operator (e.g., `signal_a ~ signal_b`).
*   **Constraints**: Use the `assert` keyword (e.g., `assert v_out is v_in * ratio`).

## Example: Voltage Divider

```atopile
module VoltageDivider:
    # External interfaces
    power = new ElectricPower
    output = new ElectricSignal

    # Components
    r_bottom = new Resistor
    r_top = new Resistor

    # Connections
    power.hv ~ r_top.p1; r_top.p2 ~ output.line
    output.line ~ r_bottom.p1; r_bottom.p2 ~ power.lv

    # Constraints
    assert power.voltage is 10V +/- 1%
    assert output.reference.voltage within 3.3V +/- 10%
```

## Reference

See [reference.md](reference.md) for details on units, tolerances, and the `->` specialization operator.
