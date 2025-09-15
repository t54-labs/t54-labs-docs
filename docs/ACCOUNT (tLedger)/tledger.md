---
title: Introduction
excerpt: Agent-native account management
deprecated: false
hidden: false
metadata:
  robots: index
---
tLedger is t54's foundational product—a blockchain-agnostic account & ledger designed to support AI agent-initiated financial transactions. It enables developers to create and manage agent-level virtual accounts, set programmable spending limits, and trigger on-chain payments.

There are multiple ways of interacting with tLedger such as API, [tLedger SDK](https://docs.t54.ai/update/docs/tledger-sdk#/), [tLedger MCP](https://docs.t54.ai/update/docs/tledger-mcp#/), and [tPortal](https://docs.t54.ai/update/docs/tportal#/) that allow developers and customers to manage agents, accounts, and risk limits in an intuitive manner. Meanwhile, tRadar automatically screens payments initiated by agents, connecting to tLedger to understand agent identity and risk levels.

![](https://files.readme.io/7cbfd45b64348a7f1c07d8a4a87b8fcfae7a8527f191ee7796009ad19a2ddd8f-image.png)

## Key Features

tLedger provides comprehensive infrastructure for AI agent financial operations through four core capabilities:

* **Agent Virtual Accounts** - Create, delete, and update virtual accounts for AI agents with full authentication and account management capabilities
* **Blockchain Ledger Service** - Interact with multiple blockchains, enabling transaction recording and synchronization with blockchain ledgers across different networks
* **Payment Protocol** - Standard on-chain payment protocol handling sender-to-receiver transactions, including blockchain-based payment information, addresses, and payment purposes
* **Framework Integration** - Native plugins for mainstream agent frameworks, including LangChain, Vercel, GAME by Virtual Protocols and XRPL Agentic Stack.

## Ways to connect to tLedger

There are multiple ways of connecting with tLedger based on your individual and/or business needs.

* **tLedger API - External API endpoints providing programmatic access to t54 backend**
* **tLedger SDK - Software development kit for seamless integration (consolidating former tPay SDK)**
* **tPortal - Web-based UI portal for managing agent accounts, viewing transaction history, monitoring risk profiles, and configuring security settings**
* **t54 MCP - Model Context Protocol-compatible connections enabling Claude agents to directly utilize tLedger services, create agent accounts, and initiate financial transactions**
