---
name: migrate
description: >
  Safe database and dependency migrations. Use when the task concerns this subject.
---

# Safe database and dependency migrations

Before a schema or dependency change, explain its effect on posted records, invariants, existing data, compatibility, deployment, rollback, and recovery. Preserve audit history; never treat a destructive down migration as proof of safe recovery. Review generated SQL, backups, data validation and operational rollout, and test against representative PostgreSQL data as appropriate. Use available source and CLI tools when specialized MCP tools are unavailable. Proceed only within approved scope.
