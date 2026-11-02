---
paths:
  - "**/*.ts"
  - "**/*.tsx"
---

# Expo Rules

Apply these rules only to projects that depend on `expo`, whichever platforms they target.

## Tooling

- Read the documentation for the installed SDK version before using its APIs.

## Components

- Define styles with `StyleSheet.create`.
- Use `Pressable` instead of the `Touchable*` components.

## Build

- Reload through the development server for JavaScript-only changes. Run `npx expo run:ios` or `npx expo run:android` after native dependency or `app.json` changes.
- Run `npx expo export --platform web` to build for browsers.
- Run `npx expo prebuild --clean` only when needed, because it discards manual changes in `ios/` and `android/`, including the signing team.
