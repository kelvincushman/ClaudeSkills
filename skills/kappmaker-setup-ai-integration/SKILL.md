---
name: kappmaker-setup-ai-integration
description: Guides the setup of secure AI backend functions (OpenAI/Replicate) for KAppMaker. Use when the user wants to "add AI features", "setup OpenAI", or "integrate Replicate".
---

# KAppMaker AI Integration

Guides the setup of the secure, serverless backend for AI features.

## Instructions

1.  **Firebase Plan**: Ensure the project is on the **Blaze plan**.
2.  **Secrets**: Store `OPENAI_API_KEY` or `REPLICATE_API_KEY` in **Google Cloud Secret Manager**.
3.  **Deploy**: Run `firebase deploy --only functions` from the `Web` root folder.
4.  **Config**: Update `util/Constants.kt` with the `CLOUD_FUNCTIONS_URL`.

## Configuration
```kotlin
const val CLOUD_FUNCTIONS_URL = "https://REGION-PROJECT_ID.cloudfunctions.net"
```
