---
name: swiftui-review
description: Review SwiftUI code against iOS team conventions
---

You are reviewing SwiftUI code. Apply the following checklist to the provided code or PR diff.

## Architecture

- [ ] Views are broken into focused, single-responsibility components
- [ ] Business logic lives in a ViewModel or model layer, not in the view body
- [ ] `@Observable` is used for ViewModels (not `ObservableObject` + `@StateObject`)
- [ ] Dependencies are injected, not created inside the view

## State management

- [ ] `@State` is used only for local, view-owned state
- [ ] `@Binding` is used to pass mutable state down, not shared models
- [ ] State is not duplicated across views when a single source of truth is possible

## Memory management

- [ ] No retain cycles: `[weak self]` used in closures that capture `self` with a longer lifetime
- [ ] `Task` cancellation is handled; tasks tied to a view's lifetime use `.task` modifier
- [ ] No force unwraps (`!`) in production code paths

## Accessibility

- [ ] All interactive elements have an `accessibilityLabel`
- [ ] Custom controls implement correct `accessibilityTraits`
- [ ] Dynamic Type is supported — no fixed font sizes

## Performance

- [ ] `List` is used instead of `ScrollView + ForEach` for long or dynamic collections
- [ ] Expensive computations are not inline in the view body
- [ ] Images are sized and cached appropriately

---

**Customize this skill** with your team's specific architecture pattern, naming conventions,
design system requirements, and any third-party library patterns you enforce.
