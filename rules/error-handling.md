---
alwaysApply: true
description: Errors, validation, and invariant enforcement.
---
# Error handling

- Represent expected failures clearly and map HTTP errors to consistent Problem Details. Adopt a Result type only when it adds value; exceptions remain appropriate for exceptional failures.
- Establish a safe exception boundary when the API requires one; never expose sensitive internal details. Do not scaffold unrelated infrastructure during design or outside an approved task.
- Validate external input at boundaries. Domain objects must protect their own invariants, and database constraints and transactions must enforce guarantees where appropriate. Boundary validation alone is insufficient.
- Avoid broad catches except at appropriate boundaries, and preserve exception context. Handle rollback, ambiguous commit outcomes, and retries explicitly for financial operations.
