---
paths:
  - "**/pyproject.toml"
---

# pyproject.toml Rules

## Dependencies

- Manage dependencies with uv, and set a 7-day cooldown:

  ```toml
  [tool.uv]
  exclude-newer = "7 days"
  ```

- When a newer release is required, such as for a security fix, exempt only that package with `exclude-newer-package`.
- Declare dependencies with lower bounds (`>=`), not exact pins (`==`). Exact versions belong in the lockfile.
- Use `==` only for sibling packages released in lockstep with this one. Within one repository, reference them as workspace members or path sources instead.
