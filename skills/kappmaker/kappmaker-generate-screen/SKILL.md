---
name: kappmaker-generate-screen
description: Generates a new screen in a KAppMaker project using the MVVM/MVI pattern. Use when the user wants to "add a new screen", "create a profile screen", or "generate screen boilerplate".
---

# KAppMaker Screen Generation

This skill automates the creation of a new screen, ensuring architectural consistency and adherence to KAppMaker's naming conventions.

## Instructions

1.  **Determine Names**: Use the provided screen name (e.g., `Profile`) for PascalCase and convert to snake_case (e.g., `profile`) for file paths and routes.
2.  **Create Directory**: Create the directory `composeApp/src/commonMain/kotlin/{{package_path}}/presentation/screens/{{screen_name_lowercase}}`.
3.  **Generate Files**: Create the following four files:
    *   `{{ScreenName}}Screen.kt`: The UI Composable.
    *   `{{ScreenName}}ScreenRoute.kt`: Navigation routing.
    *   `{{ScreenName}}UiState.kt`: UI State and Events.
    *   `{{ScreenName}}UiStateHolder.kt`: The ViewModel.

## Templates

The full template code is available in the [reference.md](reference.md) file.

## Examples

See the [examples.md](examples.md) file for concrete usage scenarios.

## Post-Generation
Remind the user to update the Dependency Injection (DI) setup in `AppInitializer` by including `factoryOf(::{{ScreenName}}UiStateHolder)`.
