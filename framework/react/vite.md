---
paths:
  - "**/*.ts"
  - "**/*.tsx"
  - "**/*.css"
---

# Vite Rules

Apply these rules only to projects that depend on `vite`.

## Tooling

- Add a framework or component library only when it clearly earns its place.
- When the repository also contains a backend, place the web UI in `frontend/`. When a Python backend serves it, build into the package's static directory and proxy `/api` to the backend during development.
- `build` must run the type check.

## Styling

- Use plain CSS with custom properties as theme tokens.
