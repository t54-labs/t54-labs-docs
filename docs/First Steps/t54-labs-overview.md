---
title: Products Overview
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
t54 labs builds an **AI native financial infrastructure for the Agent Economy**. t54 labs offers the most trustworthy and scalable solutions that enable enterprise customers to equip their agents with financial identities, accounts, and payment capabilities—backed by an agent-native risk management and compliance framework. Whether you're building an agent that shops, hires, invests, or pays, **t54 provides the infrastructure to do it safely and confidently**.

## Explore the products

<Cards columns={3}>
  <Card title="tLedger" icon="fa-database" href="/docs/tledger">
    **AI-native account management platform**

    Programmatic APIs and tools for blockchain-agnostic agent account management, enabling seamless financial identity creation and transaction processing.
  </Card>

  <Card title="tRadar" icon="fa-shield-alt" href="/docs/tradar">
    **Intelligent risk management system**

    Advanced risk assessment and fraud prevention service that powers trust and security across all t54 financial operations.
  </Card>

  <Card title="Claire" icon="fa-robot" href="https://docs.t54.ai/v1.3/docs/claire#/">
    **Financial gateway agent**

    The intelligent financial assistant that serves as the bridge between AI agents and real-world financial transactions.
  </Card>
</Cards>

### Product Components

We offer various ways to connect to our products, including agent-native approaches like our MCP integration for Claude, programmatic APIs for developers, and no-code solutions through our web portal. Whether you're building sophisticated AI agents or need simple point-and-click interfaces, t54 provides flexible integration options to match your technical requirements and use cases.

<Accordion title="tLedger" icon="fa-database">
  **Components:**

  **[tLedger API](https://docs.t54.ai/v1.3/update/reference#/)**\
  Programmatic APIs for blockchain-agnostic agent account management platform

  **[tLedger SDK](https://docs.t54.ai/v1.3/update/docs/tledger-sdk#/)**\
  Software development kit for seamless integration (consolidating former tPay SDK)

  **[tPortal](https://docs.t54.ai/v1.3/update/docs/tportal#/)**\
  Web-based UI portal for managing agent accounts, viewing transaction history, monitoring risk profiles, and configuring security settings

  **[t54 MCP](https://docs.t54.ai/v1.3/update/docs/tledger-mcp#/)**\
  Model Context Protocol (MCP) compatible connections enabling Claude agents to directly utilize tLedger services, create agent accounts, and initiate financial transactions

  [Learn More →](tledger)
</Accordion>

<Accordion title="tRadar" icon="fa-shield-alt">
  **Components:**

  **tRadar API** *(Work in Progress)*\
  Standalone service accessible via simple API for third-party integration

  **[Embedded functionality](https://docs.t54.ai/v1.3/update/docs/%EF%B8%8Fpayments-risk-control#/)**\
  Powering risk assessment within Claire and tLedger products

  [Learn More →](tradar)
</Accordion>

<Accordion title="Claire" icon="fa-robot">
  **Components:**

  **Claire Agent**\
  The financial gateway agent

  **Claire Card** *(Planned)*\
  Physical payment device enabling real-world transactions paired with financial agents

  [Learn More →](https://docs.t54.ai/v1.3/docs/claire#/)
</Accordion>

<Image border={false} src="https://files.readme.io/05068be2ce2cc890a154559ac85f8b0e19681057ac8777e562490c88ef74ed46-image.png" />

## What you can do with t54

Start from a [Quick Start](/docs/getting-started)!

t54 enables agent developers to equip AI agents with core financial primitives—without the need to rebuild financial infrastructure from scratch. More importantly, when failure, fraud, or loss occurs, t54 provides peace of mind to human users by enforcing trust and guardrails—maximizing the overall customer experience.

| **Capability**                             | **Enables you to…**                                                                                                                                                                                                                     |
| ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Create agent financial profiles            | Assign each AI agent a virtual financial account, configure daily spend limits, and manage the agent's financial assets.                                                                                                                |
| Trigger agent-to-agent payments            | Enable your agents to send payments to other agents or third-party t54 agents using secure, programmable infrastructure.                                                                                                                |
| Delegate payments securely                 | Leverage t54's KYA (Know Your Agent) and validator agents to verify behavior, enforce credit caps, and prevent fraud or hallucinated transactions.                                                                                      |
| Build merchant payout rails                | Integrate compliant payout flows to human merchants—allowing agents to pay for services, subscriptions, or contractual work.                                                                                                            |
| Unlock agent monetization                  | Set up fee-sharing structures and reward tokens so agents can earn for completed tasks—similar to SaaS-style commissions or usage-based incentives.                                                                                     |
| Integrate seamlessly with agent frameworks | Connect directly with agent orchestration tools like [Virtual Protocol's GAME](https://github.com/game-by-virtuals/game-python/tree/main/plugins/tLedger), [MCP](https://www.anthropic.com/news/model-context-protocol), and REST APIs. |
| Audit and analyze                          | Track balances, review transaction history, and export logs for compliance or analytics—accessible via API or the t54 Portal.                                                                                                           |

<br />
