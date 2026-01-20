---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: kappmaker-setup-logging
description: Configures the AppLogger and optional Telegram Bot logging in KAppMaker. Use when the user wants to "setup logging", "enable telegram logs", or "log an error".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# KAppMaker Logging

This skill manages application logging using `AppLogger` and configures the optional Telegram Bot for instant error notifications.

## Usage

```kotlin
AppLogger.i("Info message")
AppLogger.e("Error message", throwable)
AppLogger.d("Debug message")
```

## Telegram Configuration

1.  **Get Token**: Create a bot via `@BotFather` on Telegram.
2.  **Get Chat ID**: Use `https://api.telegram.org/bot<Token>/getUpdates` after messaging the bot.
3.  **Update File**: Set `TELEGRAM_BOT_TOKEN` and `TELEGRAM_CHAT_ID` in the `TelegramLogger` file.

## Reference

See [reference guide](references/REFERENCE.md)(reference.md) for detailed steps on getting Telegram credentials.
