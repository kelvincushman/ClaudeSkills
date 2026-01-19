---
name: kappmaker-setup-authentication
description: Guides the setup of Firebase Authentication providers in KAppMaker. Use when the user wants to "add Google login", "setup Apple sign-in", or "configure authentication".
---

# KAppMaker Authentication

Guides the setup for integrating Firebase Authentication providers.

## Instructions

1.  **Firebase Console**: Enable the provider in the Firebase Console.
2.  **Config Files**: Ensure `google-services.json` and `GoogleService-Info.plist` are in place.
3.  **Platform Setup**:
    *   **Google**: Set `GOOGLE_WEB_CLIENT_ID` in `local.properties`.
    *   **Apple**: Configure the `.p8` key in Firebase and add the capability in Xcode.
