---
title: tledger API
deprecated: false
hidden: false
metadata:
  robots: index
next:
  pages:
    - slug: payment-create_payment
      title: Create Payment
      type: endpoint
---
This page provides a high-level walkthrough of the most important tLedger API endpoints and how they map to common agent workflows. For full schema details and exhaustive endpoint documentation, please refer to the [API Reference](https://docs.t54.ai/reference/payment-create_payment#/).

# Authentication

All API requests must include the following headers:

```
X-API-Key: your_api_key
X-API-Secret: your_api_secret
```

API keys can be generated from the tLedger Portal (Coming Soon).

# System Hierarchy: Project vs Agent Profile vs Account

To help developers understand how tLedger structures financial operations, here's a brief overview of the hierarchy:

## Project

A Project acts as the top-level financial and operational container.

Created by developers or companies.

Includes a treasury agent to manage the overall fund.

Centralized configuration like network and daily transaction limit.

## Agent Profile

Represents a financial identity for an individual AI agent.

Each agent belongs to one Project.

Treasury agents manage project funds; operational agents carry out actions.

Has a daily transaction limit and associated multi-asset accounts.

## Account

An account is linked to an agent and holds a specific asset (e.g., SOL, USDT).

Agents can have multiple accounts.

Multiple accounts can share the same blockchain wallet address within a network.

# Key Endpoints by Workflow

## Create a Project

```
POST /api/v1/projects
```

Initializes a new project as a financial container with a treasury agent.

## Onboard an Agent

```
POST /api/v1/agent_profiles
```

Registers an AI agent under a project and provisions its accounts (e.g., USDT/SOL).

## Initiate a Payment

```
POST /api/v1/payment
```

Sends funds from one agent to another. Use this to trigger payments between agents via tLedger.

## Retrieve Agent Details

```
GET /api/v1/agent_profiles/{agent_id}
```

Fetches agent metadata, virtual accounts, balances, and limits.

## Monitor Account Balance

```
GET /api/v1/accounts/{account_id}
```

Get the latest account details and balance for a specific asset.

## Delete a Project or Agent

```
DELETE /api/v1/projects/{project_id}
DELETE /api/v1/agent_profiles/{agent_id}
```

Clean up unused entities as needed during testing or reset.

# Full Reference

Looking for full request/response schemas, status codes, and examples?

Visit the [API Reference](https://docs.t54.ai/reference/payment-create_payment#/) for complete documentation.