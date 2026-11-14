---
alwaysApply: true
description: Security and data protection for the ledger.
---
# Security

- Never hardcode or commit real secrets. Use suitable secret storage for each environment and parameterized SQL for database access.
- Validate untrusted input at boundaries while maintaining domain and database invariants independently.
- Define authorization and access boundaries deliberately when introduced. Authentication is deferred from the initial milestone; clearly document and limit exposure until it exists.
- Protect transport and data according to deployment and threat context; use established cryptography and key management rather than inventing encryption. Configure CORS deliberately where browser access requires it.
- Minimize sensitive data in logs at every level and in every environment; never log credentials or tokens. Consider audit integrity separately from application logging.
