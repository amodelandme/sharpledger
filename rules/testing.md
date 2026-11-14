---
alwaysApply: true
description: Financial verification and testing.
---
# Testing

- Choose tests for the guarantee: focused domain tests for financial rules; API tests for contracts; real PostgreSQL integration tests for constraints, transactions, isolation, concurrency, and rollback where applicable.
- An in-memory provider or mocked repository cannot demonstrate PostgreSQL guarantees. Testcontainers is an option when appropriate, not a prerequisite for every test.
- Cover failure, duplicate request, concurrency, and recovery scenarios as the behavior requires. Document what remains unverified.
- Test observable behavior rather than implementation details. Use clear Arrange/Act/Assert structure, descriptive names, and isolated test data; share expensive fixtures safely.
