---
alwaysApply: true
description: Readable and consistent C# conventions.
---
# Coding style

- Favor clear names, consistent formatting, narrow visibility, and straightforward code. Use file-scoped namespaces and descriptive async method names where appropriate.
- Prefer cohesive files and types; use one type per file as a convention when useful, not a reason to split tightly related trivial declarations.
- Use records, primary constructors, pattern matching, and other language features when they improve clarity. Their use does not replace validation or invariants. Monetary value objects must prevent invalid states and use exact representations.
- Seal types not intended for inheritance where appropriate, and make visibility no broader than necessary.
