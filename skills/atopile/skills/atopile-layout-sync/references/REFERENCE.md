# Atopile Layout Reference

## KiCAD Plugin
The plugin is automatically installed when you run `ato`. If missing, run `ato configure` to re-trigger installation.

## Layout Reuse Rules
- Layouts are mapped to **classes or super-classes** that have a build target.
- To create a reusable layout, add a build config with `ato create build` and point it at your module.
- The "Pull" (Down arrow) button in the plugin pulls layout data from the module's KiCAD file.
