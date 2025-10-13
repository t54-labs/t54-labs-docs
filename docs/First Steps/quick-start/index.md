---
title: Quick Start
hidden: false
next:
  pages:
    - slug: tledger-backend-sdk
      title: tLedger Backend Sandbox
      type: basic
    - slug: tledger-toolkit
      title: tLedger Toolkit
      type: basic
    - slug: api-schema-endpoints
      title: API Schema & Endpoints
      type: basic
---
<br />

# Quick Start

Choose your path to get started with the **t54 Trust Stack**.
Whether you’re integrating agentic finance into an organization or building your own autonomous financial agent, start with the flow that matches your use case.

<Tabs>
  <Tab title="Business (Default)">
    ### Getting Started for Businesses

    The **Business** path is designed for institutions, platforms, and developers integrating t54 into existing payment or compliance workflows.

    <Cards columns={3}>
      <Card href="https://docs.t54.ai/v1.4/docs/tledger#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600 }}>
          Create a tLedger Account
        </div>

        <div align="center">
          Set up a programmable financial account with built-in compliance, custody, and settlement logic.
        </div>
      </Card>

      <Card href="https://docs.t54.ai/v1.4/docs/tledger-sdk#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600 }}>
          Integrate with tLedger SDK
        </div>

        <div align="center">
          Use the SDK to embed account creation, payments, and compliance flows directly into your product.
        </div>
      </Card>

      <Card href="https://docs.t54.ai/v1.4/docs/trustline#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600 }}>
          Connect via Trustline x402 Facilitator
        </div>

        <div align="center">
          Enable secure agent-to-agent payments using the x402 interoperability standard.
        </div>
      </Card>
    </Cards>
  </Tab>

  <Tab title="Individual">
    ### Getting Started for Individuals

    The **Individual** path is for users and creators who want to experience personal agentic finance.

    <Cards columns={3}>
      <Card href="https://docs.t54.ai/v1.4/docs/claire#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600 }}>
          Create Your Agent — Claire
        </div>

        <div align="center">
          Build your personal AI financial gateway to automate payments, savings, and budgeting.
        </div>
      </Card>

      <Card>
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600 }}>
          Connect to Trustline (Coming Soon)
        </div>

        <div align="center">
          Soon you’ll be able to connect Claire directly to Trustline for real-time protection and transparency.
        </div>
      </Card>

      <Card>
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600 }}>
          More to Come
        </div>

        <div align="center">
          Stay tuned for personal agent verification, P2P agent payments, and self-hosted dashboards.
        </div>
      </Card>
    </Cards>
  </Tab>
</Tabs>

***

### Next Steps

Once your setup is complete, explore:

* [**Integrate with KYA →**](https:)

<br />

<br />

<br />

<br />

<br />

<br />

tRadar Service API

tLedger Onboarding

Base App

Claire Agents

based on use case:

I am individual, creating my own financial gateway agents

I am base app users, I want to protect my fund

I am agent developers, secure my agentic payment with t54 labs e2e solutions

I am x402, AP2, A2A protocol developers, I want to protect my agents payments

<br />

<br />

<br />

<br />

Welcome to t54, the AI-native financial infrastructure platform. Follow these steps to start building autonomous financial capabilities for your AI agents.

## 1. Create an account in sandbox

Open t54's **[sandbox console](https://portal-sandbox.t54.ai/)** and create an account to begin your development journey. If you're in the development phase and need access to an online test environment, we provide a Sandbox for safe testing:

**Sandbox Base URL:** [https://api-sandbox.t54.ai/api/v1](https://api-sandbox.t54.ai/api/v1)

Learn more about our [Sandbox vs Production environments](https://docs.t54.ai/v1.2/update/docs/production-vs-sandbox#/).

**Ready for launch?** When it's time to go live, simply create an account in the **[production console](https://portal.t54.ai/)** and replicate the resources you need.

## 2. Create your first project

If you've just created an account for the first time, you'll be taken directly to the project creation process. Add the name to your project and continue.

<Image border={false} src="https://files.readme.io/3a3975574eba50dd96f7fe06fe3f4208af5736688820268dcceca76940c2fce0-image.png" />

<br />

## 3. Get your API keys

In the **security tab of your project** you will find the client and server API keys you need to integrate t54 into your application.

<Image align="center" border={false} width="30% " src="https://files.readme.io/7f225f3f59c969743dc78feb62cb9a83e7029353ff5c9516db683d1a928b1e68-image.png" />

## 4. Explore our products

Now you're ready to explore what t54 can do! You can dive into our three core products:

* **[tLedger](/docs/tledger)** - Agent-native account management and blockchain transactions
* **[tRadar](/docs/tradar)** - AI-native compliance and risk management framework
* **[Claire](/docs/claire)** - The financial gateway agent

## 5. Start with some use cases!

Before diving into the technical architecture and implementation details like SDK and APIs, we encourage you—especially if you're a developer, whether or not you've already built your own agent—to begin by exploring these use cases...

<Cards columns={3}>
  <Card title="Autonomous Shopping Assistant" icon="fa-shopping-cart" href="/docs/shopping-assistant">
    AI agents that can browse, compare prices, and make purchases autonomously while managing budgets and payment approvals.
  </Card>

  <Card title="Agentic Monopoly Game" icon="fa-dice" href="/docs/monopoly-game">
    Interactive game demonstrating agent-to-agent transactions, property management, and automated financial decision-making.
  </Card>

  <Card title="Global Payroll" icon="fa-globe" href="https://docs.t54.ai/v1.3/update/docs/global-payroll#/">
    Leverage Claire and tLedger capabilities: Receive payroll from 60+ countries, while making personal financial asset management and risk assessment
  </Card>
</Cards>
