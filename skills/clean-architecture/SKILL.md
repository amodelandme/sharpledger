---
name: clean-architecture
description: >
  Dependency boundaries and application design. Use when the task concerns this subject.
---

# Dependency boundaries and application design

Preserve Domain independence, Application coordination, Infrastructure implementation, and thin API delivery. The API composition root may reference Infrastructure for registration. Organize within those boundaries by capability when useful. Discuss focused persistence ports and other alternatives rather than prescribing a repository or DbContext abstraction. Avoid adding a mediator, generic layers, or projects without demonstrated value. Show how transaction boundaries and database constraints reinforce domain guarantees.
