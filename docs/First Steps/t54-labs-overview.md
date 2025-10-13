---
title: Products Overview
excerpt: The Trust Layer for the Agent Economy
deprecated: false
hidden: false
metadata:
  robots: index
---
t54 labs builds an **AI-native trust layer for the agent economy.**  
Our mission is to **re-engineer financial trust** for a world where AI agents act, transact, and make financial decisions on behalf of humans.

The **t54 Trust Stack** delivers three core layers:

1. **Identity & Verification** – verifying *who acts and why*  
2. **Risk & Fraud** – detecting anomalies, abuse, and model-drift in real time  
3. **Platform** – unifying identity, risk, and settlement into programmable infrastructure  

Together, these components form a complete trust layer across any blockchain, agent framework, or payment rail.

---

## Product Overview

<Cards columns={3}>

<Card title="KYA: Know Your Agent" href="/docs/kya">
**Agent-native identity verification**

Beyond KYC/KYB — cryptographically verifies *who the agent is, who it represents, and why it acts.*  
Combines code audits, device posture, and intent proofs tied to merchant, asset, and time.
</Card>

<Card title="tRadar" href="/docs/tradar">
**Real-time risk and fraud intelligence**

A continuous trust monitor evaluating agent behavior and transaction context.  
Detects anomalies, fraud, and manipulation using agent-behavioral and financial signals.
</Card>

<Card title="tLedger" href="/docs/tledger">
**Unified trust and settlement platform**

Blockchain-agnostic account, risk, and compliance engine that brings verified identity and trusted decisions directly into settlement.
</Card>

</Cards>

---

## Product Components

### Identity & Verification — Know Your Agent (KYA)

KYA defines *who acts and why.* It extends traditional compliance frameworks to cover agents as autonomous actors.

**Core Features**
- Agent code audit and signature validation  
- Human–agent identity binding via ASID biometric trust  
- Cryptographic intent proofs (merchant, asset, time)  
- Delegated authorization and validator agent checks  

**Integrations**
- **ASID hardware proof layer** (fingerprint/palm ZKP hardware from Claire Card — *coming soon*)  
- **API:** `/api/v1/agent_profiles` (create, verify, limit, delete)  

[Learn more →](kya)

---

### Risk & Fraud — tRadar

tRadar is the agent-native risk engine that underpins every t54 product. It applies multi-layer scoring across behavioral, transactional, and model signals to defend against fraud, abuse, and model-drift.

**Components**
- **tRadar API (Beta):** External interface for agent risk scoring  
- **Embedded Risk:** integrated directly into tLedger payment and account flows  
- **Validator Network:** distributed agents validating risk decisions across ecosystems  

**Example Use Cases**
- Detecting hallucinated or replayed payments  
- Real-time anomaly scoring for autonomous spending  
- Risk-adjusted approvals and transaction challenges  
- Credit caps, daily limit enforcement, and model drift detection  
- Guardrailed AI delegation with programmable recourse  

[Learn more →](tradar)

---

### Platform — tLedger

tLedger powers verified, auditable, and programmable agent accounts.  
It integrates blockchain rails (Solana, Base, XRPL) and fiat channels under one schema.

**Core APIs**
- `POST /api/v1/projects` → create AI project & treasury  
- `POST /api/v1/agent_profiles` → onboard agent identity  
- `POST /api/v1/payment` → execute agent-to-agent payment  
- `GET /api/v1/payments` → query transactions  

**Key Features**
- Virtual account management and treasury limits  
- Multi-asset support (SOL, USDT, RLUSD, etc.)  
- Risk-aware settlement using tRadar signals  
- Integrated compliance via KYA validation  

**SDKs & Interfaces**
- **tLedger SDKs:** Python + TypeScript for GAME/Eliza agents  
- **tPortal:** Web UI for account, key, and risk management  
- **MCP Integration:** Claude agents can call tLedger natively  

[Learn more →](tledger)

---

## What You Can Build with t54

| **Capability** | **Enables you to…** |
|-----------------|--------------------|
| **Create agent financial profiles** | Assign each AI agent a verified financial identity with compliance and credit controls. |
| **Delegate and verify agent actions** | Bind each action to a verified identity and intent proof using KYA. |
| **Monitor financial transaction risk in real time** | Detect anomalies via tRadar; pause, challenge, or block agent-initiated transactions. |
| **Prevent fraud and model abuse** | Use continuous behavioral scoring to identify hallucinated payments or manipulation attempts. |
| **Execute compliant payments** | Transfer funds securely through verified agents using tLedger APIs. |
| **Analyze and audit activity** | Access risk logs, balances, and transaction history via API or Portal for compliance. |

---

[Quick Start →](/docs/getting-started)
