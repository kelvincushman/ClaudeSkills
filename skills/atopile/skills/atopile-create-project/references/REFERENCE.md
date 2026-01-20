# Atopile Project Structure Reference

## Default Project Files

| File/Directory | Purpose |
| :--- | :--- |
| `LICENSE` | Default MIT license. |
| `README.md` | Project description. |
| `ato.yaml` | Atopile's configuration file (defines entry point, dependencies, etc.). |
| `build/` | Build artifacts and cache (should be ignored by Git). |
| `layouts/` | KiCAD layout files. |
| `layouts/default/default.kicad_pcb` | The main layout file updated by `ato build`. |
| `*.ato` | Your Atopile source files (e.g., `demo.ato`). |

## `ato.yaml` Entry Point

The `ato.yaml` file specifies the entry point for the build process, typically a module named `App` in your main `.ato` file.
