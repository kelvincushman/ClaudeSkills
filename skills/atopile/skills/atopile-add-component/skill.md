---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: atopile-add-component
description: Adds a component to an Atopile project, either by auto-picking passive components or by fetching a specific part. Use when the user wants to "add a resistor", "add a capacitor", or "fetch a specific part".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# Atopile Component Addition

This skill helps in adding components to the `.ato` source file.

## 1. Auto-Pick Passive Components

For passive components (resistors, capacitors, inductors), define the requirements in the `.ato` file:

```atopile
resistor = new Resistor
resistor.resistance = 10kohm +/- 5%
resistor.package = "0402"
```

## 2. Add Specific Component

Use the CLI tool to fetch a part and add its pinout, footprint, and 3D model to the project:

```bash
ato create part
```

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for details on creating custom parts and using the package registry.
