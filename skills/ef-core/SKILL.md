---
name: ef-core
description: >
  EF Core persistence with financial integrity. Use when the task concerns this subject.
---

# EF Core persistence with financial integrity

EF Core is a persistence tool, not a guarantee of financial correctness. Discuss mapping and persistence boundaries without mandating direct DbContext access or a repository. Preserve immutable posted records, exact amounts, database constraints, atomicity, isolation, and concurrency guarantees through explicit design and PostgreSQL integration tests. Review bulk updates/deletes and raw SQL carefully. Apply optimizations only when justified and verify version-sensitive behavior using official documentation.
