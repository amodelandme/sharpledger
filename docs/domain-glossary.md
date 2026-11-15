# Domain Glossary

These definitions use the wallet business's perspective unless stated otherwise. Examples are learning aids, not final product or architectural decisions.

- **Ledger:** A record of financial positions and activity.
- **Ledger account:** A record that tracks a particular financial position or category, such as bank cash or an amount owed to a customer.
- **Cash at bank:** An asset account that tracks the wallet company’s money held at a bank. Money received increases it with a debit. Money paid out decreases it with a credit.
- **Asset:** Something the business holds or is owed. Bank cash is an example.
- **Liability:** An obligation the business owes. A customer wallet balance can represent an amount the wallet business owes that customer.
- **Revenue:** Income earned by the business from its activities, such as a fee charged for a service.
- **Account classification:** The accounting category of a ledger account, such as asset or liability.
- **Account identifier:** A distinct reference used to identify a ledger account, independently of a potentially shared or changing name.
- **Account status:** The account’s lifecycle state, such as open or closed. SharpLedger can use it to determine whether an account is eligible for a posting.
- **Account balance:** A summary of the financial effects recorded against an account. For example, a customer wallet liability balance can represent the amount owed to that customer.
- **Opening balance:** The initial amount recorded for an account through a balanced journal entry. The offsetting line identifies where the amount came from or how it was previously recorded.
- **Currency:** The unit in which a monetary amount is expressed, such as USD or EUR. Amounts in different currencies cannot simply be added together.
- **Debit and credit:** The left and right sides of an accounting entry. A debit increases an asset or decreases a liability; a credit decreases an asset or increases a liability.
- **Journal entry:** A record of the accounting effects of an event, made up of lines identifying accounts, amounts, and debit or credit direction. A posted entry must balance: total debits equal total credits in each currency.
- **Posting:** Recording an entry as part of the ledger's financial history. Posted entries must be preserved; corrections use explicit entries rather than silently changing history.
- **Posting eligibility:** Whether an account may receive a journal line under the applicable ledger rules. A wallet’s ability to spend or withdraw is governed separately.
- **Atomic posting:** Posting all lines of an entry together, or posting none of them, including when a failure occurs.
- **Reversal:** A new entry that offsets an earlier entry while preserving both in the history. Whether a reversal is permitted in a particular situation can depend on product rules.
- **Refunds Payable:** A liability account that tracks refunds the company owes. A credit records the obligation, and a debit clears it when the company pays.
- **Idempotency key:** An identifier used to recognize a retry. The same key and request must not create a second financial effect; reuse with different request details is rejected.
- **Concurrent operations:** Operations that overlap in time. Balance checks and posting must be coordinated when product rules prohibit spending the same funds twice.
- **Entity:** In domain modeling, an object distinguished by its identity over time, even when some of its attributes change. A ledger account is a candidate entity.
- **Value object:** In domain modeling, an object whose meaning is determined by its value rather than a distinct identity.
