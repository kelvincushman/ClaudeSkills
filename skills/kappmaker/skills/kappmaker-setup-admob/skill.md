---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: kappmaker-setup-admob
description: Configures Google AdMob Ads (Banner, Interstitial, Rewarded) in KAppMaker. Use when the user wants to "add ads", "setup admob", or "show a rewarded ad".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# KAppMaker AdMob Integration

This skill manages the integration of Google AdMob ads.

## Instructions

1.  **Enable**: Set `IS_ADS_ENABLED` to `true` in `FeatureFlagManager`.
2.  **Ad IDs**: Add IDs to `local.properties` (Android) and `BaseConfig.xcconfig` (iOS).
3.  **Usage**:
    *   **Banner**: `AdmobBanner()`
    *   **Interstitial**: `rememberInterstitialAdDisplayer()`
    *   **Rewarded**: `rememberRewardedAdDisplayer()`

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for preloading ads and detailed configuration.
