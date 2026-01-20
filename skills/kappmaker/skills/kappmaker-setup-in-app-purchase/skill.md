---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: kappmaker-setup-in-app-purchase
description: Configures RevenueCat for in-app purchases and subscriptions in KAppMaker. Use when the user wants to "setup subscriptions", "add in-app purchases", or "configure revenuecat".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# KAppMaker In-App Purchases

This skill guides the setup of RevenueCat for cross-platform subscriptions and purchases.

## Instructions

1.  **API Keys**: Add `REVENUECAT_ANDROID_API_KEY` and `REVENUECAT_IOS_API_KEY` to `local.properties`.
2.  **Entitlements**: Default is "Premium". Update `PAYWALL_PREMIUM_ENTITLEMENT` in `Constants.kt` if changed.
3.  **Paywall**: Toggle `SHOW_REMOTE_PAYWALL` in `Constants.kt` to switch between RevenueCat's remote UI and the local `PaywallScreen`.

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for platform-specific setup (Google Play Console / App Store Connect).
