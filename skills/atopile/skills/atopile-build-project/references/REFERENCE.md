# Atopile Build Reference

## Build Process Steps
1.  **Parsing**: Reads `.ato` files and dependencies.
2.  **Solving**: Resolves all `assert` constraints and calculates component values.
3.  **Picking**: Selects specific components from the library (e.g., LCSC).
4.  **Netlisting**: Generates the connectivity map for KiCAD.
5.  **Layout Sync**: Updates the `.kicad_pcb` file with new components and nets.

## CLI Options
- `--help`: Show all commands and options.
- `--target`: Specify a build target defined in `ato.yaml`.
- `--config`: Path to a custom `ato.yaml`.
