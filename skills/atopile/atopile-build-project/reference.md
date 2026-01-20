# Atopile Build Process Reference

## Build Steps

When you run `ato build`, the compiler performs the following steps:

1.  **Read `ato.yaml`**: Locates the entry point.
2.  **Compile Code**: Starts from the entry point.
3.  **Solve Equations**: Solves systems of constraints (e.g., for resistor values).
4.  **Pick Components**: Selects components from the parts library that satisfy all constraints.
5.  **Update PCB File**: Generates or updates the KiCAD layout file (`default.kicad_pcb`).
6.  **Generate Manufacturing Data**: Creates Gerber files and other manufacturing outputs.
7.  **Generate Reports**: Creates BOMs and other reports.

## Debugging

Use `ato --debug build` to run a `debugpy` server on port `5678`, allowing you to connect a debugger from VSCode/Cursor.
