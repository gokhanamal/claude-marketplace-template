---
name: code-review
description: Review Android/Kotlin code against team conventions
---

You are reviewing Android/Kotlin code. Apply the following checklist to the provided code or PR diff.

## Architecture

- [ ] Code follows the team's chosen architecture (MVVM, MVI, or Clean Architecture)
- [ ] ViewModels do not hold references to Activity or Fragment contexts
- [ ] Repository layer handles data sources; UI layer does not query databases or network directly

## Coroutines and Flow

- [ ] Coroutines are launched in the correct scope (`viewModelScope`, `lifecycleScope`)
- [ ] Flows collected in UI are collected with `repeatOnLifecycle` to respect lifecycle
- [ ] Exceptions in coroutines are handled; no silent failures in `launch` blocks

## Jetpack Compose (if applicable)

- [ ] Composables are stateless where possible; state is hoisted
- [ ] Side effects use the correct effect handler (`LaunchedEffect`, `SideEffect`, `DisposableEffect`)
- [ ] `remember` is used appropriately to avoid unnecessary recompositions

## Memory and resources

- [ ] No Context leaks: Activity context not stored in long-lived objects
- [ ] Resources (cursors, streams, bitmaps) are closed after use
- [ ] Background work uses WorkManager for deferrable tasks, not foreground services

---

**Customize this skill** with your team's specific architecture pattern, library choices (Hilt, Room, Retrofit),
naming conventions, and any Compose design system requirements.
