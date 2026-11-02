---
paths:
  - "**/*.swift"
---

# Swift Rules

## Tooling

- Use the latest stable Swift language mode.
- Use the platform's standard package manager for dependencies.

## Concurrency

- Use `async`/`await`, actors, and `@MainActor`. Do not use `DispatchQueue` or completion handlers in new code.
- Do not suppress concurrency diagnostics with `@unchecked Sendable` or `nonisolated(unsafe)` unless the safety reason is stated.

## Safety

- Force unwraps, `try!`, and `as!` are prohibited outside tests.
- Do not use `print`. Use `Logger` when logging is needed.
- Handle errors with `throws` and domain-specific error types. Do not discard them with `try?` unless absence is the intended result.

## Modeling

- Prefer `struct` and `enum`. Make classes `final`.
- Model finite states with enums with associated values, and do not use `default` when switching over your own enums.
- Name booleans with `is`, `has`, `can`, or `should`.

## Structure

- Define one primary type per file.
- Split a type when it takes on more than one responsibility.

## Tests

- Cover logic with unit tests.
