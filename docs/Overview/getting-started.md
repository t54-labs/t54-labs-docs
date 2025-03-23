---
title: Quick Start
excerpt: >-
  Create a financial profile for your agent and learn how to start using t54
  labs.
hidden: false
---
Welcome to the T54 developer experience. This guide helps you get a fast, hands-on feel for what you can build with the tLedger system today — even before our full portal and advanced services go live.

***

# 1. Choose Your Starting Point

Depending on your use case and technical preference, here’s where to begin:

* **Build and test locally →** [tLedger Backend Sandbox](../sdk-api-references/tledger-backend-sandbox)\
  Set up a full local instance of the T54 backend. Ideal for full-stack developers who want to simulate the full ledger system.

* **Integrate payments into your AI agent →** [tLedger Agent Toolkit](../sdk-api-references/tledger-toolkit)\
  Install our Python package and embed TLedger payment APIs directly into your agent codebase.

* **Understand key endpoints and workflows →** [API Schema & Endpoints](../sdk-api-references/api-schema-and-endpoints)\
  Learn how projects, agents, accounts, and payments are structured in TLedger.

***

### 2. Try a Minimal Example (Agent-to-Agent Payment)

Here’s a minimal way to simulate a TLedger payment:

* Create a project using the `POST /api/v1/projects` endpoint
* Register two agent profiles using `POST /api/v1/agent_profiles`
* Use the `POST /api/v1/payment` endpoint to initiate a payment from Agent A to Agent B

See [API Schema & Endpoints](../sdk-api-references/api-schema-and-endpoints) for examples and response formats.

***

### 3. What’s Coming Next

* **TLedger Portal (coming soon):** Visual project and agent management dashboard
* **tRadar & tPay modules:** Compliance framework and real-world value payments
* **Demo videos and live testnet:** In progress

***

### 💡 Tip

Join early, test freely, and help us shape the next-generation AI-agent finance infrastructure.

***