---
title: x402-Secure
deprecated: false
hidden: false
metadata:
  robots: index
next:
  description: >-
    _For continuous updates and advanced use cases, visit the [x402-secure
    GitHub page](https://github.com/t54-labs/x402-secure)._
---
**Open-Source SDK & Proxy for Secure Agent Payments on x402 — powered by Trustline from [t54](https://t54.ai)**

<Anchor label="![Production Proxy](https://img.shields.io/badge/Production%20Proxy-4C51BF?logo=cloudflare&logoColor=white)" target="_blank" href="https://x402-proxy.t54.ai">![Production Proxy](https://img.shields.io/badge/Production%20Proxy-4C51BF?logo=cloudflare&logoColor=white)</Anchor> <Anchor label="![GitHub Repo](https://img.shields.io/badge/GitHub%20Repo-181717?logo=github&logoColor=white)" target="_blank" href="https://github.com/t54-labs/x402-secure">![GitHub Repo](https://img.shields.io/badge/GitHub%20Repo-181717?logo=github&logoColor=white)</Anchor> <Anchor label="![Server on x402scan](https://img.shields.io/badge/Server%20on%20x402scan-0A84FF?logo=google-chrome&logoColor=white)" target="_blank" href="https://www.x402scan.com/server/655c6f59-88df-4bf2-99c5-42e392322c84">![Server on x402scan](https://img.shields.io/badge/Server%20on%20x402scan-0A84FF?logo=google-chrome&logoColor=white)</Anchor>  <Anchor label="![Website](https://img.shields.io/badge/Website-FF624A?logo=google-chrome&logoColor=white)" target="_blank" href="https://www.x402secure.com/">![Website](https://img.shields.io/badge/Website-FF624A?logo=google-chrome&logoColor=white)</Anchor>

<Image border={false} src="https://files.readme.io/5b640dbe63a104d13462a5c4a1b616b370070900260b6eed9d5552aea2a6cc44-G4RWR3ZWcAA6LuN.jpeg" />

<br />

***

## 1. Overview

**x402-secure** is the open-source gateway that connects AI agents to **[Trustline](https://docs.t54.ai/docs/trustline#/)**, t54’s agent-native risk engine.
Together, they enable **safe, accountable, and compliant** agent-to-agent or agent-to-service payments.

### What Trustline Provides

* Logic-level risk assessment on the agent’s reasoning chain
* Real-time fraud and anomaly detection
* Cryptographic evidence for dispute resolution
* Agent-native compliance and audit trails

### What x402-secure Adds

* Agent SDK for trace collection
* Facilitator proxy aligned with the x402 payment protocol
* Liability protection for both agent developers and service providers
* Production-grade proxy integrated with Trustline’s real-time risk layer

### x402-secure now supports Base and Solana

**x402-secure** is fully compatible with both chains through the x402 protocol.  Agents settling payments on Base or Solana receive the same pre-transaction risk assessment, behavioral verification, and liability attribution offered by [Trustline](https://docs.t54.ai/docs/trustline#/).

### Example Use Case: x402 Monopoly

A full end-to-end autonomous agent economy built on x402-secure.  
See the live docs here: [https://docs.t54.ai/docs/x402-monopoly#/](https://docs.t54.ai/docs/x402-monopoly#/)

***

## 2. Quick Start

This section helps you spin up the proxy locally for testing.

### Prerequisites

* Python 3.11 or 3.12
* [uv](https://astral.sh/uv) package manager

### Setup

```bash
# 1. Clone repository
git clone https://github.com/t54-labs/x402-secure
cd x402-secure

# 2. Create virtual environment & install dependencies
uv venv
uv sync

# 3. Copy and configure environment
cp env.example .env
```

Edit `.env` and update:

```bash
PROXY_LOCAL_RISK=1
PROXY_UPSTREAM_VERIFY_URL=https://x402.org/facilitator/verify
PROXY_UPSTREAM_SETTLE_URL=https://x402.org/facilitator/settle
```

### Run the Proxy

```bash
uv run python run_facilitator_proxy.py
```

Verify with:

```bash
curl http://localhost:8000/health
```

**Common issues**

* `500 risk endpoints`: ensure `PROXY_LOCAL_RISK=1` for local testing.
* Port conflict: adjust `PROXY_PORT` in `.env` or free port 8000.

**Next steps**

* See full developer guide at [docs/DEVELOPMENT.md](https://github.com/t54-labs/x402-secure/blob/main/docs/DEVELOPMENT.md)
* Browse sample integrations under [examples/](https://github.com/t54-labs/x402-secure/tree/main/packages/x402-secure/examples)

***

## 3. Why x402-secure

### The Challenge

If you build AI agents that transact:

* How do you prevent unauthorized purchases?
* Who bears liability when an agent errs?
* How do you prove the agent’s reasoning was sound?

If you run APIs or services accepting agent payments:

* How do you verify agent-initiated transactions?
* How do you resolve disputes automatically?

### The Solution

x402-secure enforces clear, verifiable responsibility boundaries through:

* Reasoning trace capture
* Real-time risk evaluation via Trustline
* Immutable evidence storage
* Programmatic dispute protection

***

## 4. For AI Agent Developers

**Use Case:** you’re building an agent that spends on behalf of users.

### What You Get

* Automatic liability coverage for approved transactions
* Evidence of reasoning for every payment
* Risk checks before settlement
* SDK with simple integration

### Integration (Python Example)

```python
pip install x402-secure

from x402_secure_client import BuyerClient, BuyerConfig, RiskClient, OpenAITraceCollector
from x402_secure_client import store_agent_trace, execute_payment_with_tid

buyer = BuyerClient(BuyerConfig(
    seller_base_url="https://api.example.com",
    agent_gateway_url="https://x402-proxy.t54.ai",
    buyer_private_key=YOUR_PRIVATE_KEY
))

risk = RiskClient("https://x402-proxy.t54.ai")
session = await risk.create_session(agent_did=buyer.address, app_id="my-agent-v1")
sid = session["sid"]

tracer = OpenAITraceCollector()
# ...collect reasoning stream...
tid = await store_agent_trace(risk, sid, "purchase_item", {"item": "coffee maker"}, tracer.events)

payment = await execute_payment_with_tid(
    buyer, "/api/purchase", "purchase_item",
    {"item": "coffee maker"}, sid, tid
)
```

For full SDK reference, see [Buyer Integration Guide](https://github.com/t54-labs/x402-secure/blob/main/docs/BUYER_INTEGRATION.md).

***

## 5. For API / Service Providers

**Use Case:** your API accepts agent payments.

### What You Get

* Risk score attached to each transaction
* Proof-of-intent for disputes
* Seamless integration via standard x402 headers

### Example Integration (FastAPI)

```python
from fastapi import FastAPI, Request
from fastapi.responses import JSONResponse
from x402_secure_client import SellerClient

app = FastAPI()
seller = SellerClient("https://x402-proxy.t54.ai/x402")

@app.get("/api/service")
async def service(request: Request, param: str):
    # define payment requirements
    reqs = {"network": "base-sepolia", "maxAmountRequired": "100000", "asset": "0x...USDC"}
    xpay = request.headers.get("X-PAYMENT")
    secure = request.headers.get("X-PAYMENT-SECURE")
    sid = request.headers.get("X-RISK-SESSION")
    if not all([xpay, secure, sid]):
        return JSONResponse({"accepts": [reqs]}, status_code=402)

    result = await seller.verify_then_settle(json.loads(base64.b64decode(xpay)), reqs,
                                             x_payment_b64=xpay, x_payment_secure=secure,
                                             risk_sid=sid)
    return JSONResponse({"status": "ok", "result": result})
```

Detailed server integration guide: [Seller Integration Guide](https://github.com/t54-labs/x402-secure/blob/main/docs/SELLER_INTEGRATION.md)

***

## 6. How It Works

**Flow summary**

1. Agent creates a risk session via the proxy.
2. Reasoning trace collected and stored by Trustline.
3. Agent sends payment with risk headers through x402.
4. Proxy validates payment, consults Trustline, and settles upstream.
5. Result returned with signed evidence.

<Image border={false} src="https://files.readme.io/b4142fcd8215266c24b7662f65b70706d2fd2c5dd0fe1b91e434c089aafb1afb-image_3.png" />

***

## 7. Resources

* [Developer Documentation](https://github.com/t54-labs/x402-secure/tree/main/docs)
* [tLedger Quick Start](../tledger-toolkit)
* [Trustline Risk Engine](../trustline-overview)
* [Agentic Finance Overview](../agentic-finance)
* [Play x402 Monopoly](https://www.x402secure.com/)

For questions or support: **[support@t54.ai](mailto:support@t54.ai)**
Community: [discord.gg/t54labs](https://discord.gg/t54labs)
