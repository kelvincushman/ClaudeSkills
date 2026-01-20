# Atopile Package Management Reference

## Dependency File (`ato.yaml`)

Dependencies are listed in the `ato.yaml` file:

```yaml
dependencies:
  - type: registry
    identifier: atopile/buttons
    release: 0.2.2
```

## Development Dependencies

You can install dependencies from Git or a local directory:

*   **Git**: `ato add git://{git-url}`
*   **Local**: `ato add file://./path/to/package`

**Note**: You cannot publish a package that depends on unpublished packages.
