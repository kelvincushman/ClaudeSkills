---
name: atopile-define-module
description: Defines modules, components, and interfaces in the .ato language. Use when creating new circuit blocks, defining component properties, or structuring the design hierarchy.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Module Definition

This skill guides you through defining the core building blocks of an Atopile design: modules, components, and interfaces.

## Core Concepts

- **Module**: A reusable block of circuitry (like a class).
- **Component**: A specialized module representing a physical part.
- **Interface**: A collection of electrical signals (e.g., I2C, Power).

## Basic Syntax

```ato
module MyModule:
    signal_a = new ElectricSignal
    gnd = new Electrical
    
component MyResistor from Resistor:
    package = "0402"
    resistance = 10kohm +/- 1%
```

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for advanced syntax, inheritance, and built-in types.
- See [usage examples](examples/examples.md) for common module patterns.
