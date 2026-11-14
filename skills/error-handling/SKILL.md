---
name: error-handling
description: >
  Design API errors and validation. Use when the task concerns this subject.
---

# Design API errors and validation

Represent expected failures clearly and use consistent Problem Details for HTTP errors. Choose Result types where useful rather than mandating one. Validate at external boundaries, protect invariants in domain objects, and enforce applicable guarantees in PostgreSQL. Handle unexpected exceptions at appropriate boundaries without leaking sensitive information. Explain transaction rollback and ambiguous commit outcomes for financial writes.
