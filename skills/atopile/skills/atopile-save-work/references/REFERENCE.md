# Atopile Version Control Reference

## Sample `.gitignore`
```gitignore
# Atopile build artifacts
build/

# Atopile dependency cache
.ato/

# KiCAD backup files
*.bak
*-bak
*.kicad_pcb-bak

# OS generated files
.DS_Store
Thumbs.db
```

## What to Version
- `.ato` source files.
- `ato.yaml` configuration.
- `layouts/` (KiCAD project and PCB files).
