# Kotlin Coding Standards & Rules

This document outlines the mandatory coding styles and rules for this project. These rules are designed to improve readability, maintainability, and consistency across the codebase.

## 1. Imports
* **No Wildcard Imports:** Never use asterisk imports (e.g., `import kotlinx.android.*`). 
* **Explicit Imports:** Each class or function must be imported individually. This prevents namespace pollution and makes dependencies explicit.
    * *Android Studio Fix:* `Settings > Editor > Code Style > Kotlin > Imports` -> Select **Use single name import**.

## 2. Naming Conventions

### Variables (val and var)
* **Format:** `camelCase`
* **Rule:** All local variables, properties, and member variables must start with a lowercase letter and use camelCase for subsequent words.
* **Example:**
    ```kotlin
    val userProfileImage: String = "url"
    var retryCount: Int = 0
    ```

### Constants (const val)
* **Format:** `SCREAMING_SNAKE_CASE` (e.g., `FIRST_LAST`)
* **Scope:** Must **always** be defined at the **top-level** (outside of any `class` or `object` scope).
* **Rule:** Do not place constants inside `companion object` blocks.
* **Example:**
    ```kotlin
    // ✅ Correct: Outside class scope
    const val MAX_RETRY_ATTEMPTS = 3
    const val BASE_URL_KEY = "BASE_URL_KEY"

    class NetworkClient { ... }
    ```

## 3. Function Parameters & Arguments

### Multi-line Formatting
* **Threshold:** If a function definition or a function call has **more than 2 parameters**, it must be formatted across multiple lines.
* **Rule:** Each parameter/argument must reside on its own line.

### Named Arguments
* **Rule:** Always use **Named Arguments** when a function call is multi-lined. This ensures clarity on what each value represents.
* **Example:**
    ```kotlin
    // ✅ Correct multi-line formatting with named arguments
    updateUser(
        id = 101,
        name = "John Doe",
        email = "john.doe@example.com",
        isActive = true
    )
    ```

## 4. Enforcement
To keep these rules consistent, please ensure your Android Studio "Code Style" settings are synced and consider running `./gradlew detekt` before pushing changes.
