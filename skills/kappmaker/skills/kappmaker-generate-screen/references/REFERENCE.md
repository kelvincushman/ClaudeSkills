# Screen Generation Reference

## File Naming Conventions

For a screen name `{{ScreenName}}` (e.g., `Profile`), the following suffixes are used:

| File Name | Purpose | Suffix |
| :--- | :--- | :--- |
| `{{ScreenName}}Screen.kt` | Screen Composable (UI Rendering) | `Screen` |
| `{{ScreenName}}ScreenRoute.kt` | Navigation Class (Screen Routing) | `ScreenRoute` |
| `{{ScreenName}}UiState.kt` | UI State Class and Events | `UiState` / `UiEvent` |
| `{{ScreenName}}UiStateHolder.kt` | ViewModel Class (State Management) | `UiStateHolder` |

## Dependency Injection (DI) Requirement

After generating the files, the `AppInitializer` must be updated to include the new ViewModel in the presentation module's DI setup:

```kotlin
// Example DI setup in AppInitializer.kt
module {
    // ... other factories
    factoryOf(::{{ScreenName}}UiStateHolder)
}
```

## Template Details

The templates include standard imports and boilerplate for:
*   **State Flow**: `val uiState: StateFlow<{{ScreenName}}UiState>` in the ViewModel.
*   **Event Handling**: A basic `onEvent()` function in the ViewModel.
*   **Navigation**: A `navigateTo{{ScreenName}}()` extension function for `NavController`.
