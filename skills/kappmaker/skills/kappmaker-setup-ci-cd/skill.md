---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: kappmaker-setup-ci-cd
description: Configures GitHub Actions CI/CD for KAppMaker. Use when the user wants to "setup github actions", "configure ci/cd", or "automate app publishing".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# KAppMaker CI/CD Setup

This skill guides the configuration of GitHub Actions for automated building and publishing of Android and iOS apps.

## Instructions

1.  **Workflows**: Ensure `build.yml`, `publish_android_playstore.yml`, and `publish_ios_appstore.yml` are in the `.github/workflows` directory.
2.  **Secrets**: Guide the user to add the required GitHub Repository Secrets (see [reference.md](reference.md)).
3.  **Triggers**:
    *   **Build**: Runs on push to `main` or PR.
    *   **Android Publish**: Runs on tag ending with `-android`.
    *   **iOS Publish**: Runs on tag ending with `-ios`.

## Detailed Reference

For the full list of required secrets and generation commands, refer to the [reference.md](reference.md) file.
