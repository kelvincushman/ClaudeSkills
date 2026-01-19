---
name: kappmaker-run-script
description: Executes KAppMaker utility scripts for versioning and data layer generation. Use when the user wants to "update app version", "generate local data layer", or "run a project script".
---

# KAppMaker Utility Scripts

This skill manages the execution of built-in project scripts for common development tasks.

## Available Scripts

### 1. Update Version
Increments version code and sets version name for both Android and iOS.
```bash
chmod +x scripts/update_version.sh
./scripts/update_version.sh -v "1.0.5"
```

### 2. Create Local Data Layer
Generates Entity, DAO, Mapper, and DI bindings for a model.
```bash
./scripts/make_local.sh YourModelName
```

## Reference

See [reference.md](reference.md) for details on what each script generates.
