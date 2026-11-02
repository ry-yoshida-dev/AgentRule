---
paths:
  - "**/*.ts"
  - "**/*.tsx"
---

# TypeScript Rules

## Configuration

- Enable `strict`, `noUncheckedIndexedAccess`, and `noFallthroughCasesInSwitch`.
- `typecheck` and `lint` scripts must exist and pass before work is complete.

## Typing

- `any`, `@ts-ignore`, and non-null assertions are prohibited. Use `@ts-expect-error` only with a stated reason.
- Annotate the return types of exported functions.
- Model finite states with discriminated unions, and handle them in a `switch` with an exhaustive `never` check.
- Parse external data into domain types at the boundary instead of asserting its type with `as`.
- Mark domain data as `readonly`.

## Naming

- Name boolean values with `is`, `has`, `can`, or `should`.
