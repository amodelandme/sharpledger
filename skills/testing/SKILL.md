---
name: testing
description: >
  Testing financial rules and persistence guarantees. Use when the task concerns this subject.
---

# Testing financial rules and persistence guarantees

Use focused domain tests for invariants, API tests for contracts, and real PostgreSQL integration tests for transactional, constraint, isolation, rollback, and concurrency guarantees. Testcontainers is an option where appropriate. Do not treat in-memory databases or mocks as proof of PostgreSQL behavior. Prefer meaningful behavior assertions, isolated data, readable test structure, and explicit reporting of unverified conditions.
