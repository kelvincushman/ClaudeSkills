---
name: kappmaker-create-network-client
description: Generates a pre-configured Ktor HttpClient for a new API in KAppMaker. Use when the user wants to "add a new API client", "connect to a remote service", or "create a network client".
---

# KAppMaker Network Client

Generates a pre-configured Ktor `HttpClient` instance with standard features.

## Instructions

1.  **Create Factory**: Create `{{ClientName}}Factory.kt` in `data/source/remote`.
2.  **Update DI**: Add the new client to the Dependency Injection configuration in `AppInitializer.kt`.

## Template
```kotlin
fun {{ClientName}}Factory(baseUrl: String, tokenProvider: () -> String) = HttpClient {
    install(ContentNegotiation) {
        json(Json { ignoreUnknownKeys = true })
    }
    install(DefaultRequest) {
        url(baseUrl)
        header("Authorization", "Bearer ${tokenProvider()}")
    }
}
```
