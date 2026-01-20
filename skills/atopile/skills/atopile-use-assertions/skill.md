---
name: atopile-use-assertions
description: Uses assertions and mathematical constraints to validate designs and solve for component values. Use when defining circuit requirements, calculating resistor values, or checking tolerances.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Assertions and Constraints

This skill enables you to use the Atopile solver to validate your design and automatically calculate component values based on physical constraints.

## Basic Usage

Use the `assert` keyword to define relationships between attributes.

```ato
assert v_out within 3.2V to 3.4V
assert r_total is r_top.resistance + r_bottom.resistance
```

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for supported operators and solver behavior.
- See [usage examples](examples/examples.md) for complex constraint systems.
