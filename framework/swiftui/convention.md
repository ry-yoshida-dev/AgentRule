---
paths:
  - "**/*.swift"
---

# SwiftUI Rules

Apply these rules to every project that uses SwiftUI, whichever platform it targets.

## State and Navigation

- Use `@Observable`. Do not use `ObservableObject` or `@Published`.
- Use `NavigationStack` or `NavigationSplitView`. Do not use `NavigationView`.

## Structure

- Keep domain logic independent of SwiftUI, and place screens under `Features/`.
- Do not let stores become catch-all types.

## Views

- Keep `body` readable by extracting sub-views into their own types.
- Add a `#Preview` for each reusable view that does not require device-only resources.
- Use string catalogs for user-facing text.
