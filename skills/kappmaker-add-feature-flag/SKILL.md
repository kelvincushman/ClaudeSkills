---
name: kappmaker-add-feature-flag
description: Adds a new remote feature flag to KAppMaker. Use when the user wants to "add a feature flag", "control a feature remotely", or "setup remote config".
---

# KAppMaker Feature Flag

Adds a new feature flag key for remote configuration via Firebase Remote Config.

## Instructions

1.  **Add Key**: Add a `const val` to `FeatureFlagManager.Keys`.
2.  **Usage**: Use `featureFlagManager.getBool()` to retrieve the value.

## Example
```kotlin
// In FeatureFlagManager.Keys
const val {{FLAG_NAME}} = "{{remote_key}}"

// Usage
val isEnabled = featureFlagManager.getBool(FeatureFlagManager.Keys.{{FLAG_NAME}})
```
