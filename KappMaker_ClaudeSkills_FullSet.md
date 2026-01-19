# Comprehensive Claude Code Skills for KAppMaker Boilerplate

**Author:** Manus AI
**Date:** January 19, 2026
**Source Documentation:** KAppMaker Documentation [1]

This document defines a comprehensive set of Claude Code Skills designed to automate common development tasks within a KAppMaker project. These skills ensure adherence to the project's Clean Architecture (Domain, Data, Presentation) and best practices for feature implementation.

---

## Skill 1: Screen Generation (kappmaker_generate_screen)

**Purpose:** Automates the creation of a new screen, including all necessary files for the MVVM/MVI pattern (Screen, ScreenRoute, UiState, UiStateHolder).

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `screen_name` | `string` | Yes | The desired name for the new screen (PascalCase). | `Profile` |

**Implementation Steps for Claude:**
1.  **Determine Names:** Use `screen_name` (e.g., `Profile`) for PascalCase and convert to snake\_case (e.g., `profile`) for file paths and routes.
2.  **Create Directory:** Create the directory `presentation/screens/{{screen_name_lowercase}}`.
3.  **Generate Files:** Write the boilerplate code for the four files (`Screen.kt`, `ScreenRoute.kt`, `UiState.kt`, `UiStateHolder.kt`) using the templates provided in the original `KappMakerScreenGeneratorSkill.md`.
4.  **Post-Generation Note:** Remind the user to update the Dependency Injection (DI) setup in `AppInitializer` by including `factoryOf(::{{ScreenName}}UiStateHolder)`.

---

## Skill 2: Local Storage - Room Entity (kappmaker_create_room_entity)

**Purpose:** Creates a new Room Entity and its corresponding Data Access Object (DAO) for local data persistence.

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `entity_name` | `string` | Yes | The name of the database table/entity (PascalCase). | `Task` |
| `fields` | `list<string>` | Yes | A list of field definitions (name:type). | `id:Int`, `title:String` |

**Implementation Steps for Claude:**
1.  **Create Entity:** Create `{{EntityName}}Entity.kt` in the `data/source/local` directory.
2.  **Create DAO:** Create `{{EntityName}}Dao.kt` in the `data/source/local` directory.
3.  **Update Database:** Add the abstract DAO function to `AppDatabase.kt`.
4.  **Update DI:** Add the DAO to the Dependency Injection configuration in `AppInitializer.kt` (e.g., `single { get<AppDatabase>().{{entityName}}Dao() }`).

**Code Templates:**

### Entity Template (`{{EntityName}}Entity.kt`)
```kotlin
package com.kappmaker.app.data.source.local

import androidx.room.ColumnInfo
import androidx.room.Entity
import androidx.room.PrimaryKey

@Entity(tableName = "{{entity_name_lowercase}}")
data class {{EntityName}}Entity(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    // {{fields_placeholder}}
)
```

### DAO Template (`{{EntityName}}Dao.kt`)
```kotlin
package com.kappmaker.app.data.source.local

import androidx.room.Dao
import androidx.room.Delete
import androidx.room.Query
import androidx.room.Upsert
import kotlinx.coroutines.flow.Flow

@Dao
interface {{EntityName}}Dao {
    @Query("SELECT * FROM {{entity_name_lowercase}}")
    fun getAllFlow(): Flow<List<{{EntityName}}Entity>>

    @Upsert
    suspend fun upsert({{entityName}}Entity: {{EntityName}}Entity)

    @Delete
    suspend fun delete({{entityName}}Entity: {{EntityName}}Entity)
}
```

---

## Skill 3: User Preferences (kappmaker_add_user_preference)

**Purpose:** Adds a new key constant to the `UserPreferences` component for storing simple key-value settings.

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `key_name` | `string` | Yes | The name of the preference key (e.g., `IS_DARK_MODE`). | `IS_DARK_MODE` |
| `data_type` | `string` | Yes | The data type of the preference (`Boolean`, `String`, `Int`, `Long`, `Float`). | `Boolean` |

**Implementation Steps for Claude:**
1.  **Locate File:** Find the `UserPreferences` component file (typically in the `data/source/local` or `util` package).
2.  **Add Key:** Add a new `const val` to the `companion object Keys` within `UserPreferences` using the format `const val KEY_{{KEY_NAME}} = "key_{{key_name_lowercase}}"`.
3.  **Provide Usage:** Provide the user with the corresponding `put` and `get` method usage based on the `data_type`.

**Usage Example:**
```kotlin
// Key Definition in UserPreferences.Keys
const val KEY_{{KEY_NAME}} = "key_{{key_name_lowercase}}"

// Saving
userPreferences.put{{DataType}}({{KEY_NAME}}, {{value}})

// Retrieving
val value = userPreferences.get{{DataType}}({{KEY_NAME}}, {{default_value}})
```

---

## Skill 4: Network Client Creation (kappmaker_create_network_client)

**Purpose:** Generates a pre-configured Ktor `HttpClient` instance with standard features (JSON serialization, logging, auth header) for a new remote API.

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `base_url` | `string` | Yes | The base URL for the new API. | `https://api.example.com/v1/` |
| `client_name` | `string` | Yes | The name for the new client factory function. | `ExampleApiClient` |

**Implementation Steps for Claude:**
1.  **Create File:** Create `{{ClientName}}Factory.kt` in the `data/source/remote` directory.
2.  **Generate Client:** Use the Ktor `HttpClientFactory` template, replacing the `baseUrl` and ensuring the `tokenProvider` is included for the `Authorization` header.
3.  **Update DI:** Add the new client to the Dependency Injection configuration in `AppInitializer.kt` (e.g., `single { {{ClientName}}Factory(BASE_URL, tokenProvider) }`).

**Code Template (Based on `HttpClientFactory`):**
```kotlin
package com.kappmaker.app.data.source.remote

import io.ktor.client.*
import io.ktor.client.plugins.*
import io.ktor.client.plugins.contentnegotiation.*
import io.ktor.client.plugins.logging.*
import io.ktor.serialization.kotlinx.json.*
import kotlinx.serialization.json.Json

fun {{ClientName}}Factory(baseUrl: String, tokenProvider: () -> String) = HttpClient {
    install(ContentNegotiation) {
        json(Json {
            prettyPrint = true
            isLenient = true
            ignoreUnknownKeys = true
        })
    }

    install(Logging) {
        logger = Logger.DEFAULT
        level = LogLevel.ALL
    }

    install(DefaultRequest) {
        url(baseUrl)
        // Assumes Bearer token authentication
        header("Authorization", "Bearer ${tokenProvider()}")
    }
}
```

---

## Skill 5: AI Integration Setup (kappmaker_setup_ai_integration)

**Purpose:** Provides the step-by-step guide for setting up the secure, serverless backend for AI features (OpenAI/Replicate) using Firebase Cloud Functions.

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `api_service` | `string` | No | Specific service to focus on (`OpenAI`, `Replicate`, or `All`). | `OpenAI` |

**Implementation Steps for Claude:**
1.  **Prerequisites:** Ensure the user is on the **Firebase Blaze plan** and has the Firebase CLI installed.
2.  **Secret Management:** Instruct the user to store API keys (`OPENAI_API_KEY`, `REPLICATE_API_KEY`) in **Google Cloud Secret Manager**.
3.  **Backend Deployment:**
    *   Run `firebase login` and `firebase init functions` in the `Web` root folder.
    *   Deploy functions with `firebase deploy --only functions`.
4.  **Client Configuration:** Instruct the user to update `util/Constants.kt` with the deployed functions URL:
    ```kotlin
    const val CLOUD_FUNCTIONS_URL="https://REGION-PROJECT_ID.cloudfunctions.net"
    ```
5.  **Security Note:** Remind the user that functions are secured by default and require Firebase user authentication unless `requireAuth: false` is explicitly set in the function's validation.

---

## Skill 6: Feature Flag Addition (kappmaker_add_feature_flag)

**Purpose:** Adds a new feature flag key to the `FeatureFlagManager` for remote configuration via Firebase Remote Config.

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `flag_name` | `string` | Yes | The descriptive name for the feature flag (e.g., `IS_NEW_FEATURE_ENABLED`). | `IS_NEW_FEATURE_ENABLED` |
| `remote_key` | `string` | Yes | The corresponding key in the Firebase Remote Config console (snake\_case). | `is_new_feature_enabled` |

**Implementation Steps for Claude:**
1.  **Locate File:** Find the `FeatureFlagManager` interface.
2.  **Add Key:** Add a new `const val` to `FeatureFlagManager.Keys`.
3.  **Provide Usage:** Provide the user with the code to retrieve the flag value.

**Code Template:**
```kotlin
// In FeatureFlagManager.Keys
const val {{FLAG_NAME}} = "{{remote_key}}"

// Usage Example
val featureFlagManager = buildProject<FeatureFlagManager>()
val isEnabled = featureFlagManager.getBool(FeatureFlagManager.Keys.{{FLAG_NAME}})
```

---

## Skill 7: Authentication Setup (kappmaker_setup_authentication)

**Purpose:** Provides the setup guide for integrating Firebase Authentication providers (Google, Apple).

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `provider` | `string` | Yes | The authentication provider to set up. | `Apple` |

**Implementation Steps for Claude:**
1.  **Firebase Console:** Instruct the user to enable the `{{Provider}}` provider in the Firebase Console.
2.  **Config Files:** Ensure `google-services.json` (Android) and `GoogleService-Info.plist` (iOS) are placed correctly.
3.  **Platform-Specific Configuration:**
    *   **Google:** Set `GOOGLE_WEB_CLIENT_ID` in Android `local.properties` and configure `Info.plist` on iOS with `GIDServerClientID`, `GIDClientID`, and `CFBundleURLTypes`.
    *   **Apple:** Instruct the user to configure the `.p8` key in the Firebase Console and add the "Sign In with Apple" capability in Xcode.
4.  **User Management Note:** Remind the user that user management is handled by `UserRepository` with methods like `logOut()`, `deleteAccount()`, and accessing `currentUser`.

---

## Skill 8: UI Component Creation (kappmaker_create_ui_component)

**Purpose:** Creates a new composable UI component within the `designsystem` module and provides instructions for focused development using Hot Reload.

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `component_name` | `string` | Yes | The name of the new composable component. | `AppPrimaryButton` |

**Implementation Steps for Claude:**
1.  **Create File:** Create `{{ComponentName}}.kt` in the `designsystem` module.
2.  **Provide Template:** Provide a basic composable function template.
3.  **Hot Reload Instructions:** Instruct the user on how to use the JVM entry point for focused development:
    *   Run `designsystem/jvmMain/kotlin/Main.kt`.
    *   Replace `AllComponentsGallery()` with `{{ComponentName}}()` in the `main` function for focused hot-reload development.
4.  **Resource Note:** Remind the user to use `UiRes` for resources within the `designsystem` module.

**Code Template:**
```kotlin
package com.kappmaker.app.designsystem.components

import androidx.compose.material3.Button
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier

@Composable
fun {{ComponentName}}(
    modifier: Modifier = Modifier,
    onClick: () -> Unit,
    text: String
) {
    Button(
        onClick = onClick,
        modifier = modifier
    ) {
        Text(text)
    }
}
```

---

## References

[1] KAppMaker Documentation. *KAppMaker*. [https://docs.kappmaker.com/](https://docs.kappmaker.com/)
[2] Push Notification. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/push-notification](https://docs.kappmaker.com/features/push-notification)
[3] Authentication. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/authentication](https://docs.kappmaker.com/features/authentication)
[4] In-App Purchases & Subscriptions. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/in-app-purchases-subscriptions](https://docs.kappmaker.com/features/in-app-purchases-subscriptions)
[5] Network. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/network](https://docs.kappmaker.com/features/network)
[6] Local Storage. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/local-storage](https://docs.kappmaker.com/features/local-storage)
[7] User Preferences. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/user-preferences](https://docs.kappmaker.com/features/user-preferences)
[8] UI Components. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/ui-components](https://docs.kappmaker.com/features/ui-components)
[9] AI Integration. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/ai-integration](https://docs.kappmaker.com/features/ai-integration)
[10] Feature Flag / Remote Config. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/feature-flag-remote-config](https://docs.kappmaker.com/features/feature-flag-remote-config)
[11] Google AdMob Ads. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/google-admob-ads](https://docs.kappmaker.com/features/google-admob-ads)
[12] Flexible Local Credit System. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/flexible-local-credit-system](https://docs.kappmaker.com/features/flexible-local-credit-system)
[13] Firebase Integration. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/firebase-integration](https://docs.kappmaker.com/features/firebase-integration)
[14] Architecture. *KAppMaker Documentation*. [https://docs.kappmaker.com/architecture/overview](https://docs.kappmaker.com/architecture/overview)
