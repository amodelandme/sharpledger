---
alwaysApply: true
description: Handling configured verification hooks.
---
# Hooks

- Use hooks that are actually configured in the environment; do not assume a particular agent, hook script, or post-test processor exists.
- Investigate failures rather than silently bypassing checks. Review automatic formatting changes and preserve intended behavior.
- Run relevant build and test commands directly when no hook provides them; report unavailable checks.
