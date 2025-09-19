---
title: Payments & Risk Control
deprecated: false
hidden: false
metadata:
  robots: index
---
The t54 Payment and Risk Control system is designed to ensure that every transaction initiated through our API or SDK is secure, auditable, and contextually verifiable. This section outlines how the system evaluates, processes, and safeguards payments using two key services: tRadar (risk control) and tAudit (code integrity validation).

<Image align="center" width="-10px" src="https://files.readme.io/447aa7e7c55bdf2ddd31978f8d9d782577610b01b0521035f650e5a2839f154d-tRadar_pentagon_security_diagram.png" />

# Transaction Submission

Every payment initiated through the API or SDK includes several key parameters beyond the basic sender/receiver and amount fields:

`trace_context`: Captures the reasoning and runtime state of the Agent issuing the transaction. This provides context for the payment's purpose and legitimacy.

`func_stack_hashes`: A cryptographically hashed representation of the Agent’s function call stack that led to the payment. These hashes must match known, audited functions.

`debug_mode`: Enables dry-run payment processing without touching the blockchain, while still executing full validation and risk logic.

These fields are required to initiate a payment and serve as the foundation for real-time risk evaluation.

# Transactional Risk Evaluation (tRadar)

Once submitted, the transaction is passed through tRadar, our real-time validator agent network (VAN). tRadar assesses risk using a multi-tiered logic engine that takes into account:

`Payment Metadata`: Amount, frequency, currency, and involved Agents.

`Agent Trust Profile`: Historical behavior and system-generated reputation scores.

`Contextual Analysis`: The runtime logic (via trace_context) and function lineage (via func_stack_hashes) are compared against previously audited, trusted paths.

`Rule Engine`: Custom business rules (e.g., project-specific limits, developer-specific thresholds) are applied before validator invocation.

Transactions are scored and assigned one of several risk levels_ (LOW, MEDIUM, HIGH, CRITICAL)_. For elevated risk levels, tRadar may issue a challenge, requiring the Agent to submit additional justification or data to proceed.

# Challenge-Response Mechanism

If a transaction is flagged, the challenge system acts as a dynamic gatekeeper. It pauses execution and returns a structured request for clarification—such as proof-of-purpose, logs, or metadata. Agents can respond programmatically and resubmit for re-evaluation. This adaptive flow balances security with user experience by reducing false rejections of legitimate activity.

# Code Auditing (tAudit)

To maintain integrity at the function level, all payment-related code must undergo validation via tAudit. During SDK initialization:

1. Functions tagged for payment are automatically extracted and normalized.
2. Code is hashed, submitted to the audit service, and matched against our audit registry.
3. Whether approved hashes are used in production payment calls or not will significantly help our validators to make judgement.

This ensures a tamper-proof audit trail linking every transaction back to a vetted implementation, deterring unauthorized behavior or malicious injection.

# Payment Execution

Payments proceed only after:

1. **The Agent is authenticated and the request validated.**
2. **The risk assessment returns an approved or resolved state.**

In production mode, the payment is submitted to the designated settlement network (e.g., Solana) and the resulting `transaction_hash` is stored. In debug mode, execution is simulated locally for safe testing and QA.

# Error & Logging

Failed transactions include error_details with granular reasoning (e.g., validation failure, trust breach, audit mismatch). All events are logged for post-mortem, compliance, and support tooling. These logs are essential for understanding edge cases and iteratively improving Agent design.
