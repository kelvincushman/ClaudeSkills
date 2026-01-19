# KAppMaker CI/CD Reference

## Required GitHub Secrets

| Secret Name | Description | Generation Command |
| :--- | :--- | :--- |
| `GRADLE_CACHE_ENCRYPTION_KEY` | For caching Gradle builds | `openssl rand -base64 16` |
| `SIGNING_KEY_STORE_FILE_BASE64` | Android Keystore (Base64) | `base64 -i path/to/keystore.jks | pbcopy` |
| `SIGNING_KEY_STORE_PROPERTIES_BASE64` | Keystore Properties (Base64) | `base64 -i path/to/keystore.properties | pbcopy` |
| `GOOGLE_PLAY_SERVICE_ACCOUNT_JSON` | Play Store Service Account | N/A (Download from Google Cloud) |
| `REVENUECAT_ANDROID_API_KEY` | RevenueCat Android Key | N/A (From RevenueCat Dashboard) |
| `REVENUECAT_IOS_API_KEY` | RevenueCat iOS Key | N/A (From RevenueCat Dashboard) |

## Workflow Files

*   **`build.yml`**: Validates pushes and PRs.
*   **`publish_android_playstore.yml`**: Deploys to Google Play Internal Track.
*   **`publish_ios_appstore.yml`**: Deploys to Apple App Store.
