---
title: Agentic Protocols
deprecated: false
hidden: false
metadata:
  robots: index
---
### Agentic Protocols

t54 supports **MCP** and **x402** out of the box — choose a protocol to get started.

{/* centered row of fixed-width cards */}
<div style={{ display: "flex", justifyContent: "center" }}>
  <Cards columns={2} style={{ gap: 24 }}>
    {/* MCP Integration */}
    <Card
      href="https://docs.t54.ai/v1.4/update/docs/tledger-mcp#/"
      style={{ width: 380, margin: "0 auto" }}
    >
      <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#FF624A" }}>
        Platform MCP
      </div>
      <div align="center">
        Connect Claude and other MCP-compatible clients to t54’s payment gateway for agent onboarding,
        balances, and payments.
      </div>
    </Card>

    {/* x402 / AP2 Integration */}
    <Card
      href="https://docs.t54.ai/v1.4/update/docs/x402-secure-quickstart#/"
      style={{ width: 380, margin: "0 auto" }}
    >
      <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#FF624A" }}>
        x402-Secure Facilitator
      </div>
      <div align="center">
        Route agent-to-agent payments via the x402 facilitator using Trustline risk headers and verifiable
        payment context.
      </div>
    </Card>
  </Cards>
</div>

***

### Learn More

Explore the official documentation for each open protocol that powers agentic interoperability.

{/* centered row of fixed-width official-docs cards (neutral color to de-emphasize) */}
<div style={{ display: "flex", justifyContent: "center" }}>
  <Cards columns={2} style={{ gap: 24 }}>
    {/* MCP Official Docs */}
    <Card
      href="https://modelcontextprotocol.io/docs/getting-started/intro"
      style={{ width: 380, margin: "0 auto" }}
    >
      <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#50463E" }}>
        Model Context Protocol (MCP)
      </div>
      <div align="center">
        Official documentation for the open protocol enabling AI agents and tools to share context securely
        across environments.
      </div>
    </Card>

    {/* x402 / AP2 Official Docs */}
    <Card
      href="https://www.x402.org/"
      style={{ width: 380, margin: "0 auto" }}
    >
      <div align="center" style={{ fontSize: "1.1em", fontWeight: 600, color: "#50463E" }}>
        x402 Protocol
      </div>
      <div align="center">
        Learn more about the emerging standard for agent-to-payment interoperability and verifiable intent exchange.
      </div>
    </Card>
  </Cards>
</div>
