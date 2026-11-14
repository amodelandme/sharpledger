---
name: tdd
description: >
  Test-driven development for ledger behavior. Use when the task concerns this subject.
---

# Test-driven development for ledger behavior

For an approved implementation, use red-green-refactor when it helps demonstrate behavior: write a meaningful failing test, implement the smallest correct change, then refactor and rerun. Domain tests establish business rules; real PostgreSQL tests establish database and transaction guarantees. Choose test infrastructure for the behavior rather than requiring every test to exercise HTTP. Include concurrent, retry, and failure cases as relevant.
