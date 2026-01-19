# AI Integration Reference

## Security and Architecture

The KAppMaker AI Integration is designed with a secure, serverless architecture:
1.  **Client-Side**: The mobile app (client) calls a Firebase Cloud Function endpoint.
2.  **Server-Side**: The Firebase Cloud Function acts as an **API Proxy**, securely retrieving the API key from **Google Cloud Secret Manager** and making the call to the external AI service (OpenAI/Replicate).
3.  **Security**: This prevents the exposure of sensitive API keys in the client-side code.

## Prerequisites

*   **Firebase Plan**: Must be on the **Blaze (pay-as-you-go) plan**.
*   **API Keys**: Must be stored in **Google Cloud Secret Manager** with the exact names:
    *   `OPENAI_API_KEY`
    *   `REPLICATE_API_KEY`

## Deployment Commands

The following commands are run from the `Web` root folder:

```bash
# Login to Firebase
firebase login

# Initialize Functions (select JavaScript)
firebase init functions

# Deploy Functions
firebase deploy --only functions
```

## Client Configuration

The deployed functions URL must be configured in the mobile app's `util/Constants.kt`:

```kotlin
// Example: https://us-central1-your-project-id.cloudfunctions.net
const val CLOUD_FUNCTIONS_URL="https://REGION-PROJECT_ID.cloudfunctions.net"
```
