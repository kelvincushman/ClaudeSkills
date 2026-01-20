---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: atopile-save-work
description: Guides the user on how to save their work and use version control (Git) with Atopile projects. Use when the user wants to "save my work", "commit changes", or "use git with atopile".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# Atopile Saving Your Work

This skill explains the recommended workflow for saving and versioning Atopile projects.

## Version Control with Git

Atopile projects are designed to be version-controlled using Git.

1.  **Initialize Git**: `git init` (if not already done).
2.  **Add Files**: `git add .`
3.  **Commit**: `git commit -m "Your commit message"`

## What to Version Control

*   `.ato` source files.
*   `ato.yaml` configuration file.
*   `layouts/` directory (KiCAD layout files).

## What to Ignore

The `build/` directory and the `.ato/` directory (dependency cache) should be added to your `.gitignore`.

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for a sample `.gitignore` file.
