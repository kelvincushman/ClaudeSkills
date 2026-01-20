# Atopile Module Definition Reference

## Units and Tolerances

Atopile supports units and tolerances to define physical attributes:

| Format | Example | Description |
| :--- | :--- | :--- |
| **Unit** | `1.23ohm`, `23.4uF`, `10V` | Defines the physical quantity. |
| **Range** | `1V to 2V` | Defines a range for a value. |
| **Tolerance** | `3uF +/- 1uF`, `4Kohm +/- 1%` | Defines the allowed deviation. |

## Specialization

The `->` operator is used to specialize a module instance to a different type:

```atopile
some_instance -> AnotherModuleType
```

This is useful for configuring a topology specified earlier.

## Imports

Use the new syntax for importing assets:

```atopile
from "where.ato" import What, Why, Wow
```
Imports are relative to the project root (`ato.yaml` location) or the standard library.
