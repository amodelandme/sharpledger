---
name: resilience
description: >
  Retries and failure handling for financial operations. Use when the task concerns this subject.
---

# Retries and failure handling for financial operations

A timeout or cancellation can leave a financial write with an unknown commit outcome. Do not retry writes or external calls merely because an error is transient: specify idempotency, duplicate detection, transaction boundaries, and reconciliation first. Retry a complete transaction only when the particular failure and database semantics permit it; test ambiguous outcomes and concurrent requests. Choose timeouts, retries, and circuit breakers only for demonstrated needs and verify current documentation.
