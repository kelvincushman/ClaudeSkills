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

## Recommended Workflow

1.  **Develop**: Write your `.ato` code.
2.  **Build**: Run `ato build` to validate and update the layout.
3.  **Layout**: Open KiCAD and perform the layout.
4.  **Save**: Save the KiCAD layout file.
5.  **Commit**: Commit both the `.ato` and `.kicad_pcb` files to Git.
