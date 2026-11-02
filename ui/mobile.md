# Mobile UI Rules

## Controls

- Give buttons icons so that they are intuitive. Icon-only buttons must have an accessibility label.
- Use a slider for parameters with a known range, and show the current value.
- Use platform-standard components and icons (e.g., SF Symbols on iOS) before building custom ones.
- Keep touch targets at least 44 points, and do not depend on hover.

## Layout

- Respect safe areas and the software keyboard.
- Support every targeted device, including iPad when targeted.
- Keep frequent actions within thumb reach, and use sheets for secondary tasks.
- Support Dynamic Type unless the design intentionally does not.

## States

- Every screen that loads data must handle loading, empty, and error states.
- Handle offline use and interruption by the app moving to the background.
- Request a permission only when its feature is used, and handle refusal.

## Verification

- After any screen change, build for the simulator and open the changed screen. Report honestly when it could not be verified visually.
