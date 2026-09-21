---
name: Expo project imports
description: Compatibility rules learned when bringing an existing Expo app into the pnpm artifact workspace.
---

When importing an existing Expo app into this workspace, keep the artifact scaffold's standard Metro configuration and use one icon package consistently across the project.

**Why:** The uploaded app's custom Metro cache override depended on a package that was not directly resolvable from the artifact, and mixing `@expo/vector-icons` with the scoped vector-icons packages caused Expo Doctor to fail.

**How to apply:** Preserve the artifact `expo/metro-config` default unless a direct Metro cache dependency is intentionally added. If the source app already uses `@react-native-vector-icons/*`, migrate scaffold-only icon imports to that package rather than adding a second icon library.