# Atopile Component Addition Reference

## Creating Custom Parts

For parts not available via `ato create part`, you can manually add them:

1.  Create a new folder in `project/parts/` named after your component.
2.  Add existing KiCad footprint and 3D model files to this folder.
3.  Create a `.ato` file in this folder with the same name as your component.

## Good Practice: Subclassing

When creating a component for a specific part (e.g., a specific LDO), it is good practice to subclass a generic abstract class (e.g., `LDO`) to inherit its methods and attributes:

```atopile
component Texas_Instruments_NE5532DR from LDO:
    # pin connections and attribute settings here
```
