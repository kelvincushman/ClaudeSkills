---
name: atopile-publish-package
description: Publishes Atopile modules to the public registry. Use when sharing reusable circuit blocks, contributing to the community, or managing internal component libraries.
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
---

# Atopile Package Publishing

This skill explains how to share your Atopile modules by publishing them to the public registry.

## Prerequisites

1.  **GitHub Account**: Required for authentication via OIDC.
2.  **Package Metadata**: Must be defined in `ato.yaml`.
3.  **GitHub Action**: Publishing is handled via the `atopile/publish-package` action.

## Publishing Workflow

1.  Configure `package` metadata in `ato.yaml`.
2.  Set up the GitHub Action workflow.
3.  Create a GitHub Release to trigger the publish.

## Progressive Disclosure

- See [technical reference](references/REFERENCE.md) for `ato.yaml` fields and GitHub Action configuration.
- See [usage examples](examples/examples.md) for single-package and monorepo patterns.
