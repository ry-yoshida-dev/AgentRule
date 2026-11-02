---
paths:
  - "**/*.ts"
  - "**/*.tsx"
---

# React Rules

Apply these rules to every project that depends on `react`, whichever platform it targets.

## Components

- Export one component per file, as a function component with a named props interface. Use a class only where React requires it.
- Mark props as `readonly`.
- Compute derived values during render. Use `useEffect` only to synchronize with external systems, and always clean up subscriptions.
- Keep route files thin: they compose features and do not contain business logic.
- Inline styles are for values computed at runtime only.

## Structure

- Separate code into the following directories as the project needs them: `domain/` (pure TypeScript without React), `api/` (server types and calls), `state/`, `hooks/`, `features/`, `components/`, and `theme/`.
- Keep types matching the server's API in one place under `api/`.
- Import across directories through the `@/` path alias.

## Tests

- Define a `test` script in addition to `typecheck` and `lint`, and make `lint` fail on warnings.
- Cover all domain logic with `*.test.ts` files next to the source.
