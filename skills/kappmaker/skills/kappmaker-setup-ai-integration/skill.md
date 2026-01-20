---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: kappmaker-setup-ai-integration
description: Guides the setup of secure AI backend functions (OpenAI/Replicate) for KAppMaker. Use when the user wants to "add AI features", "setup OpenAI", or "integrate Replicate".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# KAppMaker AI Integration Setup

This skill provides the step-by-step guide for setting up the secure, serverless backend for AI features (OpenAI/Replicate) using Firebase Cloud Functions.

## Instructions

1.  **Prerequisites**: Ensure the user meets the requirements detailed in the [reference.md](reference.md) file (Blaze plan, Secret Manager setup).
2.  **Backend Deployment**: Instruct the user to run the necessary Firebase CLI commands from the `Web` root folder (see [reference.md](reference.md) for commands).
3.  **Client Configuration**: Instruct the user to update `util/Constants.kt` with the deployed functions URL.

## Client Configuration Example

```kotlin
const val CLOUD_FUNCTIONS_URL="https://REGION-PROJECT_ID.cloudfunctions.net"
```

## Detailed Reference

For architectural details, prerequisites, and full deployment commands, refer to the [reference.md](reference.md) file.
