# AGENTS.md — Ledger Engineering Instructions

## Project

This project aims to build a standalone, production-grade double-entry financial ledger in C#/.NET and PostgreSQL. The current repository is an early scaffold; production readiness must be demonstrated, not assumed.

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

#### Visual Study Guides (HTML Output)

Present conceptual lessons, deep-dives, architectural walkthroughs, and study guides as self-contained HTML5 files in `docs/learning/` (e.g., `docs/learning/<topic>.html`), rather than printing dense walls of text in the terminal. Make lessons substantial enough to study beyond a single session; use multiple linked pages when useful. Continue to work through discussion questions at the learner's pace, one substantive question at a time. Reply in the terminal with only the file path and a brief summary or follow-up question. Return to the terminal for coding and implementation work. The learning guides and personal learning journal are local, ignored material.

As lessons are presented, update `docs/domain-glossary.md` with relevant terms and concise definitions. Distinguish accounting concepts from tentative design choices and product policies; do not record examples as established decisions.

End lessons at a logical stopping point and explicitly tell the learner when a lesson is complete. Aim for a scope comparable to the ledger-account foundations lesson, while adapting to the topic. Record the next step in the learning journal when the learner ends a session.

Every generated HTML file must embed all CSS inside a `<style>` tag (no external CDNs) and follow this visual design specification:

- **Color Palette (Dark Cyan Theme):**
  - Page background: Deep slate/obsidian (`#070d11`)
  - Surface/Card background: Dark petrol/slate (`#0d181f`) with subtle cyan-tinted borders (`1px solid #16323d`)
  - Primary text: Crisp off-white (`#e2eef3`), secondary/muted text (`#8aa6b2`)
  - Primary accent (headings, links, active borders, badges): Vibrant cyan (`#06b6d4` / `#22d3ee`) with subtle glowing highlights (`box-shadow: 0 0 20px rgba(6, 182, 212, 0.08)`)
  - Secondary accent (callouts/invariants): Emerald/teal (`#10b981`) for guarantees and amber (`#f59e0b`) for failure modes/pitfalls
- **Typography & Layout:**
  - Centered single-column container (`max-width: 880px; margin: 0 auto; padding: 3rem 1.5rem;`), generous `line-height: 1.7`, and clean system sans-serif fonts (`system-ui, -apple-system, sans-serif`).
  - Distinct visual hierarchy with `<h1>` gradient or bright cyan accents, `<h2>` section dividers with bottom borders, and styled comparison tables (`border-collapse: collapse`, alternating subtle row shading `#0a1318`).
- **Code & Architecture Diagrams:**
  - Render `<pre><code>` blocks in dark code wells (`#04080b`) with monospace fonts, `1px solid #132a33` borders, and cyan syntax/label headers.
  - Use clean inline SVGs or styled flexbox flow diagrams when illustrating ledger state transitions, transaction boundaries, or database schemas.
- **Interactive Elements:**
  - Include a sticky or top Table of Contents with smooth anchor scrolling.
  - Include self-check review questions at the bottom using native `<details>` and `<summary>` tags styled as interactive dark-cyan accordions.

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

## Instruction precedence and skills

The project directives in `docs/engineering-standards.md` and `docs/learning-method.md` and the operating rules above govern project decisions. Rules and skills provide supporting guidance; adapt examples to the ledger and resolve conflicts in favor of those directives. Existing decisions are not reopened without a reason. Explain important tradeoffs and ask one substantive question at a time.

Skills live in `skills/<skill-name>/SKILL.md`. Consult relevant skills selectively; examples are not automatic approval for dependencies, infrastructure, architectural decisions, or file changes. During learning and design, do not modify source files without an explicit request; approved implementation proceeds within its scope. Verify version-sensitive technical claims against current official documentation.

## Rules

Always-applied coding conventions live in `rules/`:

- `coding-style.md` -- C# 14 style, naming, file organization
- `architecture.md` -- Dependency direction, feature folders, data access
- `security.md` -- Secrets, input validation, auth, transport security
- `testing.md` -- Integration-first, xUnit v3, Testcontainers, AAA
- `performance.md` -- CancellationToken, TimeProvider, caching, async
- `error-handling.md` -- Result pattern, ProblemDetails, exception boundaries
- `git-workflow.md` -- Conventional commits, atomic commits, branch safety
- `agents.md` -- available tools, verification, skill loading
- `hooks.md` -- handling configured hooks
- `packages.md` -- compatible supported packages and dependency management
