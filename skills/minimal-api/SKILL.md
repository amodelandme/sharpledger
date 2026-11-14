---
name: minimal-api
description: >
  ASP.NET Core Minimal APIs for ledger delivery. Use when the task concerns this subject.
---

# ASP.NET Core Minimal APIs for ledger delivery

Use Minimal APIs as the delivery mechanism with explicit HTTP contracts, capability-oriented endpoints, OpenAPI, and consistent Problem Details. Handlers delegate financial operations to Application; they do not use EF Core directly or put business logic in filters. Choose explicit registration or discovery based on demonstrated value; neither requires a new abstraction by default. Verify version-sensitive behavior against official documentation.
