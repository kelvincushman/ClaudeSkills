# Atopile Publishing Reference

## `ato.yaml` Metadata
```yaml
package:
    identifier: your-github-user/package-name
    repository: https://github.com/your-github-user/package-name
    authors:
        - name: Your Name
          email: your@email.com
    summary: A brief description of the module.
    license: MIT
```

## GitHub Action Permissions
The workflow requires OIDC permissions:
```yaml
permissions:
  contents: write
  packages: write
```
