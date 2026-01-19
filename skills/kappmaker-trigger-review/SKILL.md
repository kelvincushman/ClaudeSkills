---
name: kappmaker-trigger-review
description: Triggers the in-app review/rating prompt in KAppMaker. Use when the user wants to "ask for a review", "setup app rating", or "trigger review prompt".
---

# KAppMaker In-App Review

This skill manages the built-in review trigger system with cooldown logic.

## Usage

```kotlin
val reviewTrigger = rememberInAppReviewTrigger()
LaunchedEffect(Unit) {
    reviewTrigger.triggerAfterSuccessfulPurchase()
}
```

## Custom Triggers

Add custom logic to the `InAppReviewTrigger` class. Default cooldown is 7 days (`COOLDOWN_DURATION`).

## Reference

See [reference.md](reference.md) for best practices and quota restrictions.
