---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: atopile-create-project
description: Creates a new Atopile project from the template. Use when the user wants to "start a new atopile project" or "create a new circuit design".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# Atopile Project Creation

This skill guides the user through creating a new Atopile project using the `ato create project` command.

## Usage

The command will prompt the user for project details.

```bash
ato create project
```

## Project Structure

A new project will contain:
*   `ato.yaml`: Atopile's configuration file.
*   `layouts/`: KiCAD layout files.
*   `demo.ato`: The main Atopile source file.

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for the full default project structure.
