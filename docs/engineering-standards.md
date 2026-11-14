# Project Directive: Production-Grade Financial Ledger

We have selected our project direction.

We are building a standalone, API-first, production-grade double-entry ledger engine in C#/.NET and PostgreSQL.

This is not a tutorial application, a CRUD demonstration, or a simplified accounting exercise.

The system must demonstrate the engineering discipline expected of a senior backend engineer working on financial infrastructure.

## Engineering Objectives

Prioritize:

1. Financial correctness
2. Data integrity
3. Transactional consistency
4. Concurrency safety
5. Idempotency
6. Auditability
7. Security
8. Operational reliability
9. Performance
10. Maintainability

Every important guarantee must have an explicit enforcement mechanism and a verification strategy.

## Architectural Expectations

Use a modular monolith with clearly defined domain and application boundaries.

Adopt Domain-Driven Design where appropriate.

Do not introduce abstractions without explaining their value.

Avoid premature microservices, distributed transactions, and unnecessary infrastructure.

Prefer PostgreSQL transactions and database-enforced constraints for critical financial operations.

Do not assume that EF Core abstractions automatically guarantee concurrency safety.

Do not assume that balanced journal entries alone establish financial correctness.

## HTTP API Architecture

Use ASP.NET Core Minimal APIs as the initial HTTP delivery mechanism.

Requirements:

- Organize endpoints by financial capability.
- Keep endpoint handlers thin.
- Separate HTTP contracts from domain objects.
- Place financial business rules in the Domain layer.
- Coordinate financial operations through the Application layer.
- Use standardized Problem Details responses.
- Support OpenAPI documentation and automated API testing.
- Do not introduce MediatR or a mediator abstraction without a demonstrated need.
- Do not use Entity Framework Core directly inside endpoint handlers.
- Do not place business logic inside endpoint filters.

Minimal APIs are a delivery mechanism, not the application architecture.

Reconsider controller-based APIs if future requirements justify MVC-specific capabilities.

Record this as an initial architectural decision.

## Folder Structure Example

src/
├── Ledger.Api/
│ ├── Program.cs
│ ├── Endpoints/
│ │ ├── Accounts/
│ │ │ ├── CreateAccount.cs
│ │ │ └── GetAccount.cs
│ │ ├── JournalEntries/
│ │ │ ├── PostJournalEntry.cs
│ │ │ └── GetJournalEntry.cs
│ │ └── Balances/
│ │ └── GetBalance.cs
│ └── Contracts/
├── Ledger.Application/
├── Ledger.Domain/
└── Ledger.Infrastructure/

## Financial Integrity

The design must explicitly address:

- Immutable posted journal entries
- Balanced debit and credit lines
- Exact monetary representations
- Currency consistency
- Atomic posting
- Account lifecycle and posting eligibility
- Duplicate request detection
- Concurrent posting
- Consistent balance calculations
- Reversals and corrections
- Audit trails
- Database recovery and reconciliation

Distinguish financial accounting rules from product-specific business policies.

For example, whether an account can have a negative balance is a policy decision, not a universal double-entry accounting rule.

## Engineering Verification

For each critical invariant:

1. Define the invariant.
2. Identify possible violations.
3. Identify the enforcement boundary.
4. Design automated tests.
5. Test failure conditions.
6. Document any remaining limitations.

Use real PostgreSQL integration tests for transactional guarantees.

Introduce concurrency and fault-injection tests as soon as they become relevant.

Do not describe a capability as production-ready without supporting evidence.

## Learning and Mentorship

I am learning financial accounting and fintech engineering while building this system.

You must explain the domain concepts behind architectural decisions.

Use realistic financial transactions and journal examples.

Ask me to reason through important decisions before implementing them.

Challenge my understanding.

Do not make major architectural decisions silently.

## Initial Assignment

Do not generate application code yet.

Help me define the ledger's foundational domain model.

Begin by explaining:

1. The distinction between a general ledger and a financial transaction processing system.
2. What a ledger account represents.
3. What a journal entry represents.
4. Why double-entry accounting is necessary but insufficient for financial correctness.
5. The minimum invariants required for a reliable posting engine.

Then propose an initial domain model.

Identify which objects should be entities, value objects, and aggregate roots.

Present competing approaches where reasonable.

Ask me one architectural or accounting question at a time.

Wait for my response before proceeding.

Our standard is financial infrastructure engineering, supported by demonstrable correctness rather than architectural complexity.
