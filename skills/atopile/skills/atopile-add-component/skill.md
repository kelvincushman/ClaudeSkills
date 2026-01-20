---
name: atopile-add-component
description: Adds physical components to an Atopile project. Use when selecting specific parts, assigning LCSC IDs, or defining footprints and packages.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Component Addition

This skill guides you through adding physical components to your design, either by automatic selection or by specifying exact part numbers.

## Basic Usage

Components are added by instantiating a `component` type and configuring its attributes.

```ato
import Resistor
my_res = new Resistor
my_res.package = "0603"
my_res.resistance = 1kohm +/- 1%
```

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for global attributes like `lcsc_id`, `mpn`, and `package`.
- See [usage examples](examples/examples.md) for specific part assignment and footprint configuration.
