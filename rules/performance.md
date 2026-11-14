---
alwaysApply: true
description: Evidence-driven performance and resource management.
---
# Performance

- Prefer clear asynchronous I/O and propagate cancellation where appropriate. Explain transaction boundaries and ambiguous outcomes before allowing cancellation or retry to affect a financial write.
- Use an injectable clock when time affects business behavior or testability. Manage connection, client, and other resource lifetimes deliberately.
- Measure before adopting pooling, compiled queries, ValueTask, caching, or other optimization. Simplicity and correctness take priority over speculative performance.
- Never introduce cached balances without an explicit consistency, invalidation, concurrency, and recovery design and tests appropriate to the guarantee.
