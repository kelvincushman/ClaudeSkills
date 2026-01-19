---
name: kappmaker-create-ui-component
description: Creates a new UI component in KAppMaker's designsystem module. Use when the user wants to "create a button", "add a custom view", or "build a UI component".
---

# KAppMaker UI Component

Creates a new composable UI component with Hot Reload support.

## Instructions

1.  **Create File**: Create `{{ComponentName}}.kt` in the `designsystem` module.
2.  **Hot Reload**: Run `designsystem/jvmMain/kotlin/Main.kt` and replace `AllComponentsGallery()` with `{{ComponentName}}()`.

## Template
```kotlin
@Composable
fun {{ComponentName}}(
    modifier: Modifier = Modifier,
    text: String
) {
    // Implementation
}
```
