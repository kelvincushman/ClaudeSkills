# Claude Code Skill: KappMaker Screen Generator

**Skill Name:** `kappmaker_generate_screen`
**Version:** 1.0
**Author:** Manus AI

## 1. Skill Purpose

The `kappmaker_generate_screen` skill is designed to automate the creation of a new screen within a KAppMaker project, mirroring the functionality of the native `generateNewScreen` Gradle task [1]. This skill significantly reduces development time by generating all necessary boilerplate files, ensuring architectural consistency (MVVM/MVI pattern) and adherence to KAppMaker's naming conventions.

## 2. Input Parameters

| Parameter Name | Type | Required | Description | Example |
| :--- | :--- | :--- | :--- | :--- |
| `screen_name` | `string` | Yes | The desired name for the new screen. This name will be used to generate all related file and class names. | `Settings` |

## 3. Generated File Structure

For a given `screen_name` (e.g., `{{ScreenName}}`), the skill will create the following files in the `presentation/screens/{{screen_name_lowercase}}` directory:

| File Name | Purpose | Suffix |
| :--- | :--- | :--- |
| `{{ScreenName}}Screen.kt` | Screen Composable (UI Rendering) | `Screen` |
| `{{ScreenName}}ScreenRoute.kt` | Navigation Class (Screen Routing) | `ScreenRoute` |
| `{{ScreenName}}UiState.kt` | UI State Class and UiEvent | `UiState` / `UiEvent` |
| `{{ScreenName}}UiStateHolder.kt` | ViewModel Class (State Management) | `UiStateHolder` |

## 4. Boilerplate Code Templates

The following templates use `{{ScreenName}}` as a placeholder for the user-provided screen name (e.g., `Profile`).

### 4.1. `{{ScreenName}}Screen.kt` (Screen Composable)

```kotlin
package com.kappmaker.app.presentation.screens.{{screen_name_lowercase}}

import androidx.compose.runtime.Composable
import androidx.compose.runtime.collectAsState
import androidx.compose.runtime.getValue
import androidx.lifecycle.viewmodel.compose.viewModel

@Composable
fun {{ScreenName}}Screen(
    viewModel: {{ScreenName}}UiStateHolder = viewModel()
) {
    val uiState by viewModel.uiState.collectAsState()

    // TODO: Implement the UI for {{ScreenName}}Screen
    // Use uiState to render the current state and viewModel::onEvent to handle user interactions.
}
```

### 4.2. `{{ScreenName}}ScreenRoute.kt` (Navigation Class)

```kotlin
package com.kappmaker.app.presentation.screens.{{screen_name_lowercase}}

import androidx.navigation.NavController
import androidx.navigation.NavGraphBuilder
import androidx.navigation.compose.composable

const val {{ScreenName}}_ROUTE = "{{screen_name_lowercase}}_route"

fun NavController.navigateTo{{ScreenName}}() = this.navigate({{ScreenName}}_ROUTE)

fun NavGraphBuilder.{{screen_name_lowercase}}Screen() {
    composable(route = {{ScreenName}}_ROUTE) {
        {{ScreenName}}Screen()
    }
}
```

### 4.3. `{{ScreenName}}UiState.kt` (UI State and UI Event)

```kotlin
package com.kappmaker.app.presentation.screens.{{screen_name_lowercase}}

/**
 * Represents the current state of the {{ScreenName}} screen UI.
 * Corresponds to the 'UiState' suffix.
 */
data class {{ScreenName}}UiState(
    val isLoading: Boolean = false,
    val data: String = "Initial Data"
    // TODO: Add more state variables here
)

/**
 * Represents events that can occur on the {{ScreenName}} screen.
 * Corresponds to the 'UiEvent' suffix.
 */
sealed interface {{ScreenName}}UiEvent {
    data object OnInitialLoad : {{ScreenName}}UiEvent
    data class OnButtonClicked(val value: String) : {{ScreenName}}UiEvent
    // TODO: Add more UI events here
}
```

### 4.4. `{{ScreenName}}UiStateHolder.kt` (ViewModel Class)

```kotlin
package com.kappmaker.app.presentation.screens.{{screen_name_lowercase}}

import androidx.lifecycle.ViewModel
import androidx.lifecycle.viewModelScope
import kotlinx.coroutines.flow.MutableStateFlow
import kotlinx.coroutines.flow.StateFlow
import kotlinx.coroutines.flow.update
import kotlinx.coroutines.launch

/**
 * Manages the UI state and handles UI events for the {{ScreenName}} screen.
 * Corresponds to the 'UiStateHolder' (ViewModel) suffix.
 */
class {{ScreenName}}UiStateHolder(
    // TODO: Inject dependencies here (e.g., UseCases, Repositories)
) : ViewModel() {

    private val _uiState = MutableStateFlow({{ScreenName}}UiState())
    val uiState: StateFlow<{{ScreenName}}UiState> = _uiState

    fun onEvent(event: {{ScreenName}}UiEvent) {
        when (event) {
            {{ScreenName}}UiEvent.OnInitialLoad -> handleInitialLoad()
            is {{ScreenName}}UiEvent.OnButtonClicked -> handleButtonClicked(event.value)
        }
    }

    private fun handleInitialLoad() {
        viewModelScope.launch {
            _uiState.update { it.copy(isLoading = true) }
            // TODO: Perform initial data loading
            _uiState.update { it.copy(isLoading = false, data = "Data Loaded") }
        }
    }

    private fun handleButtonClicked(value: String) {
        // TODO: Handle button click logic
        println("Button clicked with value: $value")
    }
}
```

## 5. Usage Instructions for Claude

To use this skill, the AI agent should be instructed to:

1.  **Determine** the desired `screen_name` (e.g., `Profile`).
2.  **Create** the target directory: `presentation/screens/profile`.
3.  **Substitute** all instances of `{{ScreenName}}` with the PascalCase name (e.g., `Profile`) and `{{screen_name_lowercase}}` with the snake_case name (e.g., `profile`) in the templates above.
4.  **Write** the resulting content to the four respective `.kt` files.
5.  **Remind** the user to update the Dependency Injection (DI) setup in `AppInitializer` by including `factoryOf(::{{ScreenName}}UiStateHolder)`.

## 6. References

[1] Screen Generator. *KAppMaker Documentation*. [https://docs.kappmaker.com/features/screen-generator](https://docs.kappmaker.com/features/screen-generator)
