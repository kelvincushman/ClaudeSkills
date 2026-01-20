---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: kappmaker-add-user-preference
description: Adds a new key-value preference to KAppMaker's UserPreferences. Use when the user wants to "save a setting", "store a boolean flag", or "add a user preference".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# KAppMaker User Preference

Adds a new key constant to the `UserPreferences` component for storing simple settings.

## Instructions

1.  **Add Key**: Add a `const val` to `UserPreferences.Keys`.
2.  **Usage**: Provide the user with the `put` and `get` method usage.

## Example
```kotlin
// In UserPreferences.Keys
const val KEY_{{NAME}} = "key_{{name_lowercase}}"

// Usage
userPreferences.putBoolean(KEY_{{NAME}}, true)
val value = userPreferences.getBooleadn(KEY_{{NAME}})
```
