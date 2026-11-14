---
alwaysApply: true
description: Ledger architecture and dependency boundaries.
---
# Architecture

- Preserve the selected modular monolith, explicit domain and application boundaries, and Minimal API delivery. Discuss significant changes and alternatives before adopting them.
- Domain business rules belong in the domain; application operations coordinate use cases and transactions. Keep HTTP contracts separate and endpoints thin: no direct EF Core access or financial rules in endpoint handlers or filters.
- Dependencies point inward: Domain has no infrastructure dependency; Application depends on Domain; Infrastructure implements required persistence and external capabilities. The API composition root may reference Infrastructure to register implementations.
- Organize by financial capability where useful without erasing layer boundaries. Register endpoints explicitly or through an abstraction when justified; neither auto-discovery nor manual registration is inherently mandatory.
- Choose persistence boundaries deliberately. Avoid generic wrappers that add no value, but consider focused ports or aggregate repositories where they clarify domain boundaries or transactional behavior. Discuss tradeoffs before deciding.
- Enforce module boundaries in proportion to demonstrated need. Do not add shared projects, integration events, messaging, mediators, or other infrastructure by default.
