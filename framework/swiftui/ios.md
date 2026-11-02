---
paths:
  - "**/*.swift"
---

# SwiftUI on iOS Rules

Apply these rules only to SwiftUI projects that target iOS.

## Tooling

- Use UIKit only for capabilities SwiftUI does not provide, and isolate it behind a small wrapper.

## Build

- After a change, run `xcodebuild build` against an iOS Simulator destination, and `xcodebuild test` when logic changed.
