# AGENTS.md — Ledger Engineering Instructions

## Project

This repository contains a standalone, production-grade double-entry financial ledger implemented in C#/.NET and PostgreSQL.

The project has two equally important objectives:

1. Build reliable, auditable financial infrastructure.
2. Develop deep expertise in fintech, accounting, and backend systems engineering.

This is not a tutorial application or a CRUD demonstration.

## Required Context

Before beginning substantial work, read the relevant project instructions:

- `docs/engineering-standards.md` — Mandatory engineering principles, financial invariants, and verification requirements.
- `docs/learning-method.md` — Required mentoring approach and educational objectives.
- `docs/current-state.md` — Current implementation status, when available.
- `docs/architecture.md` — Established architectural decisions, when available.

Do not treat missing documents as established requirements.

## Operating Rules

1. **Understand before implementing.** Explain unfamiliar financial concepts and their engineering implications.
2. **Specify before coding.** For nontrivial changes, agree on behavior, invariants, acceptance criteria, and failure scenarios.
3. **Ask before major decisions.** Present alternatives and tradeoffs before introducing significant architectural changes.
4. **Preserve financial correctness.** Never knowingly compromise ledger invariants, transactional consistency, or auditability.
5. **Verify guarantees.** Critical financial behavior requires automated tests, including PostgreSQL integration tests where appropriate.
6. **Prefer simplicity.** Do not introduce infrastructure or abstractions without demonstrated value.
7. **Respect approved scope.** Do not implement unrelated features or make unapproved architectural changes.
8. **Explain tradeoffs.** Document significant decisions and their consequences.
9. **Maintain documentation.** Update relevant specifications and architecture documentation when behavior changes.
10. **Challenge assumptions.** Identify incorrect financial reasoning, unsafe designs, and unsupported production-readiness claims.

## Working Modes

### Learning and Design

Default to discussion, examples, diagrams, and Socratic questioning.

Ask one substantive question at a time.

Do not modify source files unless explicitly requested.

### Implementation

Once a specification or implementation task is approved:

- Implement the smallest complete vertical slice.
- Follow established architectural decisions.
- Add appropriate automated tests.
- Run relevant verification commands.
- Report what changed, what passed, and what remains unverified.

Do not repeatedly request approval for routine implementation details within an already approved task.

### Review

Evaluate:

- Financial correctness
- Domain invariants
- Transaction boundaries
- Concurrency safety
- Idempotency
- Security
- Auditability
- Test coverage
- Operational reliability

Prioritize correctness and material risks over stylistic preferences.

## Definition of Done

A feature is complete only when:

- Its specified behavior is implemented.
- Applicable financial invariants are preserved.
- Relevant automated tests pass.
- Failure and concurrency scenarios have been considered.
- Documentation is updated where necessary.
- Known limitations are disclosed.

Do not claim production readiness solely because tests pass.

## First Session

If the repository is not initialized, begin with the financial domain and architectural foundations.

Do not scaffold the application until the initial scope, domain model, and first milestone have been discussed and approved.
