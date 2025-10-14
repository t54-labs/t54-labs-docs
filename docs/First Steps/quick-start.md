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
Choose your path to get started with the **t54 Trust Stack**.

<Tabs>
  <Tab title="Business">
    ### Getting Started for Businesses

    <Cards columns={3}>
      {/* 1) Trustline x402 Facilitator */}

      <Card href="https://docs.t54.ai/v1.4/update/docs/x402-secure-quickstart#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#FF624A" }}>
          Connect via Trustline x402-secure Facilitator
        </div>

        <div align="center">
          Enable secure agent-to-agent payments using the x402 interoperability standard.
        </div>
      </Card>

      {/* 2) tLedger Account */}

      <Card href="https://docs.t54.ai/v1.4/update/docs/tledger-quick-start#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#FF624A" }}>
          Create a tLedger Account
        </div>

        <div align="center">
          Set up a programmable financial account with built-in compliance, custody, and settlement logic.
        </div>
      </Card>

      {/* 3) tLedger SDK */}

      <Card href="https://docs.t54.ai/v1.4/update/docs/tledger-sdk#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#FF624A" }}>
          Integrate with tLedger SDK
        </div>

        <div align="center">
          Embed account creation, payments, and compliance flows directly into your product.
        </div>
      </Card>
    </Cards>
  </Tab>

  <Tab title="Individual">
    ### Getting Started as Individuals

    <Cards columns={2}>
      {/* 1) Claire Agent */}

      <Card href="https://docs.t54.ai/v1.4/docs/claire#/">
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#FF624A" }}>
          Create Your Agent — Claire
        </div>

        <div align="center">
          Build your personal AI financial gateway to automate payments, savings, and budgeting.
        </div>
      </Card>

      {/* 2) Future Features */}

      <Card>
        <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#FF624A" }}>
          More to Come
        </div>

        <div align="center">
          Personal agent verification, P2P agent payments, and self-hosted dashboards.
        </div>
      </Card>
    </Cards>
  </Tab>
</Tabs>



<Tabs>
  <Tab title="For Businesses & Developers">
    ### Getting Started for Businesses

    Below are common business and developer needs — and how t54 can help you address them.

    ---

    #### 1. “My agents need to handle money.”
    You already have AI agents (buyer, seller, or task bots) that must hold balances, receive payments, or make purchases.

    **Solution:**  
    - **[tLedger Quick Start →](https://docs.t54.ai/v1.4/update/docs/tledger-quick-start#/)**
      - Onboard your agents to create programmable financial accounts with built-in compliance, custody, and settlement logic.
    - **[tLedger SDK →](https://docs.t54.ai/v1.4/update/docs/tledger-sdk#/)**
      - For direct integration, embed account creation, payments, and compliance into your existing product or agent stack.

    ---

    #### 2. “I want to screen or verify my agents’ financial behavior.”
    Your agents already process transactions through mainstream protocols (x402, AP2, Base) and you want to assess financial risk before they act — or add a trusted layer to detect anomalies and prevent losses.

    **Solution:**  
    - **Trustline Risk API (Coming Soon)**  
      Connect your agent network to Trustline, the risk and trust engine that evaluates behavior, intent, and context in real time before transactions execute.

    ---

    #### 3. “I’m a merchant agent that needs to receive money safely.”
    Your merchant-facing agent provides goods or services and needs to accept payments without handling funds directly.

    **Solution:**  
    - **[tLedger →](https://docs.t54.ai/v1.4/update/docs/tledger-quick-start#/)**
      - Use tPortal for no-code onboarding, or integrate with tLedger SDK for code-based settlement and reconciliation.

    ---

    #### 4. “My agents transact via x402 — I want protection and dispute handling.”
    You operate buyer or merchant agents connected through x402 or AP2 protocols and need transaction assurance, dispute resolution, or loss coverage.

    **Solution:**  
    - **[x402-Secure Facilitator →](https://docs.t54.ai/v1.4/update/docs/x402-secure-quickstart#/)**
      - Integrate t54’s Trustline risk validation to secure your x402 flows and ensure transparent resolution when things go wrong.

    ---

    #### 5. “I operate a payment or agent network and want built-in trust infrastructure.”
    You’re a network provider (e.g., Mastercard, Visa, AP2, XRPL, Base) aiming to make your ecosystem agent-ready and risk-aware.

    **Solution:**  
    - **Partner with t54 Labs →**  
      Reach out to our team to integrate Trustline risk scoring, validator consensus, and dispute recovery mechanisms directly into your network.  
      [Contact Us →](mailto:contact@t54.ai)
  </Tab>

  <Tab title="For Individuals">
    ### Getting Started for Individuals

    Below are common personal scenarios — and how you can use t54 agents to automate, protect, and manage your financial life.

    ---

    #### 1. “I want an agent to manage my money.”
    You need a personal AI financial gateway to receive payroll, automate payments, and handle savings or investments.

    **Solution:**  
    - **[Claire Agent →](https://docs.t54.ai/v1.4/docs/claire#/)**
      - Create your trusted financial agent that connects to your accounts and acts safely on your behalf.

    ---

    #### 2. “I already use multiple agents in Base or other apps — I need guardrails.”
    You use AI trading or investment agents but want control over how much they can spend or risk.

    **Solution:**  
    - **Claire in Base Super App (Coming Soon)**  
      - Add Claire to your existing agent group chat — she manages custody, applies guardrails, and monitors agent activity in real time.

    ---

    #### 3. “I want my OpenAI or Claude agents to understand financial risk.”
    You’d like your conversational or reasoning agents to assess financial trust, risk exposure, or compliance before taking action.

    **Solution:**  
    - **Trustline via MCP (Coming Soon)**  
      - Connect your AI agents directly to t54’s Trustline service through the Model Context Protocol (MCP), enabling risk-aware decision-making.
  </Tab>
</Tabs>


***

### Next Steps

* [**Integrate with KYA →**](https://docs.t54.ai/v1.4/docs/kya#/)
* [**Review Trustline flows →**](https://docs.t54.ai/v1.4/docs/trustline#/)
* [**Explore Claire examples →**](https://docs.t54.ai/v1.4/docs/claire#/)
