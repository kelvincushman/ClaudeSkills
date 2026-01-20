# Atopile Publishing Examples

## GitHub Action Workflow (`.github/workflows/publish.yml`)
```yaml
on:
  release:
    types: [created]

jobs:
  release:
    if: github.event.release.draft != true
    permissions:
      contents: write
      packages: write
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: atopile/publish-package@main
```
