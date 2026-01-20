---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"
name: kappmaker-create-room-entity
description: Creates a new Room Entity and DAO for local storage in KAppMaker. Use when the user wants to "add a database table", "persist data locally", or "create a room entity".
---
license: MIT
metadata:
  author: Manus AI
  version: "1.0"

# KAppMaker Room Entity Creation

This skill creates a new Room Entity and its corresponding Data Access Object (DAO) for local data persistence.

## Instructions

1.  **Create Entity**: Create `{{EntityName}}Entity.kt` in `data/source/local`.
2.  **Create DAO**: Create `{{EntityName}}Dao.kt` in `data/source/local`.
3.  **Update Database**: Add the abstract DAO function to `AppDatabase.kt`.
4.  **Update DI**: Add the DAO to the Dependency Injection configuration in `AppInitializer.kt`.

## Templates

### {{EntityName}}Entity.kt
```kotlin
@Entity(tableName = "{{entity_name_lowercase}}")
data class {{EntityName}}Entity(
    @PrimaryKey(autoGenerate = true) val id: Int = 0,
    // Fields
)
```

### {{EntityName}}Dao.kt
```kotlin
@Dao
interface {{EntityName}}Dao {
    @Query("SELECT * FROM {{entity_name_lowercase}}")
    fun getAllFlow(): Flow<List<{{EntityName}}Entity>>

    @Upsert
    suspend fun upsert(entity: {{EntityName}}Entity)
}
```
