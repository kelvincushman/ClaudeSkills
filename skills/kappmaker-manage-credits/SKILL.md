---
name: kappmaker-manage-credits
description: Configures and manages the Flexible Local Credit System in KAppMaker. Use when the user wants to "setup credits", "add a credit reward", or "spend credits".
---

# KAppMaker Credit System

This skill manages the local credit system, including rewards, deductions, and transaction history.

## Configuration (DSL)

Define rules in `AppInitializer.kt` using `creditSystemConfig`:
```kotlin
val appCreditSystemConfig = creditSystemConfig {
    oneTimeBonus("welcome_bonus", 1)
    recurringDaily("premium_daily", 1, condition = { hasPremiumAccess() })
}
```

## Usage

```kotlin
// Add credits
creditRepository.addCredits(10, CreditTransaction.Type.PURCHASE, "10-pack")

// Use credits
creditRepository.useCredits(1, "AI Generation")
```

## Reference

See [reference.md](reference.md) for the full DSL options and UI integration details.
