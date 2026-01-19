# Screen Generation Examples

## Example 1: Creating a "Settings" Screen

**User Request:** "Create a new screen called Settings."

**Claude Action:**
1.  **Input**: `screen_name` = `Settings`
2.  **Path**: `composeApp/src/commonMain/kotlin/{{package_path}}/presentation/screens/settings`
3.  **Files Created**:
    *   `SettingsScreen.kt`
    *   `SettingsScreenRoute.kt`
    *   `SettingsUiState.kt`
    *   `SettingsUiStateHolder.kt`

**DI Update Reminder:**
"Remember to add `factoryOf(::SettingsUiStateHolder)` to your `AppInitializer`."

## Example 2: Creating a "Login" Screen

**User Request:** "I need a new screen for user login."

**Claude Action:**
1.  **Input**: `screen_name` = `Login`
2.  **Path**: `composeApp/src/commonMain/kotlin/{{package_path}}/presentation/screens/login`
3.  **Files Created**: `LoginScreen.kt`, `LoginScreenRoute.kt`, `LoginUiState.kt`, `LoginUiStateHolder.kt`.

**DI Update Reminder:**
"Remember to add `factoryOf(::LoginUiStateHolder)` to your `AppInitializer`."
