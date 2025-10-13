---
title: x402-Secure Quickstart
deprecated: false
hidden: false
metadata:
  robots: index
---
For a detailed step-by-step guide, see [docs/QUICKSTART.md](docs/QUICKSTART.md).

### Install Dependencies

```bash
# Install all dependencies including local packages
uv lock && uv sync
````

### Start the Proxy

The proxy can run in two modes:

**Development Mode** (with local in-memory risk storage):

```bash
PROXY_LOCAL_RISK=1 \
PROXY_UPSTREAM_VERIFY_URL=https://x402.org/facilitator/verify \
PROXY_UPSTREAM_SETTLE_URL=https://x402.org/facilitator/settle \
uv run python run_facilitator_proxy.py
```

**Production Mode** (with Trustline risk engine):

```bash
PROXY_LOCAL_RISK=0 \
RISK_ENGINE_URL=https://trustline-api.t54.ai \
PROXY_UPSTREAM_VERIFY_URL=https://x402.org/facilitator/verify \
PROXY_UPSTREAM_SETTLE_URL=https://x402.org/facilitator/settle \
uv run python run_facilitator_proxy.py
```

### Run Examples

After starting the proxy, you can run the example demos to see the complete payment flow.

#### Prerequisites

1. **Install Dependencies**

```bash
uv lock && uv sync
```

This installs all dependencies including the local `x402-secure` and `x402_proxy` packages in editable mode.

2. **Configure Environment**

```bash
cp env.example .env
# Edit .env file with required settings:
# - OPENAI_API_KEY: Required for buyer agent demo with AI responses
# - AGENT_GATEWAY_URL: Unified gateway base for buyer Risk API (default http://localhost:8000)
# - MERCHANT_PAYTO: Seller's receive address (default provided in env.example)
# - NETWORK: default base-sepolia
```

**For Buyer Agent Demo**, ensure these are set:

* `OPENAI_API_KEY` - Your OpenAI API key for agent tracing
* `BUYER_PRIVATE_KEY=0x...` - Required; signed X-PAYMENT is the default
* `SELLER_BASE_URL` - Default: `http://localhost:8010`
* `AGENT_GATEWAY_URL` - Default: `http://localhost:8000` (served by the proxy app)

Upstream facilitator (optional, e.g., x402.org on Base Sepolia):

* `PROXY_UPSTREAM_VERIFY_URL=https://x402.org/facilitator/verify`
* `PROXY_UPSTREAM_SETTLE_URL=https://x402.org/facilitator/settle`

#### Run the Demo

Open three terminals and run in sequence:

**Terminal 1: Start Proxy (port 8000)**

```bash
PROXY_LOCAL_RISK=1 \
PROXY_UPSTREAM_VERIFY_URL=https://x402.org/facilitator/verify \
PROXY_UPSTREAM_SETTLE_URL=https://x402.org/facilitator/settle \
uv run python run_facilitator_proxy.py
```

**Terminal 2: Start Seller (port 8010)**

```bash
PROXY_BASE=http://localhost:8000/x402 \
uv run uvicorn --app-dir packages/x402-secure/examples seller_integration:app --port 8010
```

**Terminal 3: Run Buyer Agent Demo**

```bash
AGENT_GATEWAY_URL=http://localhost:8000 \
SELLER_BASE_URL=http://localhost:8010 \
uv run python packages/x402-secure/examples/buyer_agent_openai.py
```

The buyer demo demonstrates the SDK's capabilities (using OpenAI as the current agent framework):

1. **RiskClient**: Creates a risk session with Trustline (works with any agent framework)
2. **OpenAITraceCollector**: Captures AI reasoning traces during OpenAI streaming
3. **store_agent_trace**: Submits collected traces to Trustline (framework-agnostic)
4. **build_payment_secure_header**: Generates W3C traceparent headers with trace ID
5. **BuyerClient**: Executes payment with all required risk headers
6. **Optional**: Includes AP2 evidence (mandates/attestations) for enhanced risk assessment

**Note:** `PROXY_LOCAL_RISK=1` enables local in-memory risk handling (development).
For production, set `PROXY_LOCAL_RISK=0` and `RISK_ENGINE_URL=https://trustline-api.t54.ai`.

### Observability

* Buyer demo initializes OpenTelemetry tracing; spans print to console by default.
* To view spans in a local OTEL Collector, follow [docs/observability/otel-collector-minimal.md](docs/observability/otel-collector-minimal.md).

  * Set `OTEL_EXPORTER_OTLP_ENDPOINT=http://localhost:4318/v1/traces`.
  * Optionally set `OTEL_SERVICE_NAME` (default: `buyer-demo`).

### Buyer Risk Session

* Buyer agent creates risk session via `POST /risk/session` at `AGENT_GATEWAY_URL`.
* **Local Mode** (`PROXY_LOCAL_RISK=1`): proxy handles risk in-memory.
* **Production Mode** (`PROXY_LOCAL_RISK=0`): proxy forwards to Trustline (`RISK_ENGINE_URL=https://trustline-api.t54.ai`).
* Payments include `X-RISK-SESSION` + `X-PAYMENT-SECURE` per [docs/specs/payment-trace-and-evidence-spec.md](docs/specs/payment-trace-and-evidence-spec.md).

### Base Sepolia Demo (Local Seller → x402.org Upstream)

Use localhost for the Seller URL. The proxy forwards to x402.org’s upstream facilitator on Base Sepolia.

**Network:** `base-sepolia`
**Endpoints:** `https://x402.org/facilitator/verify` and `/settle`

Run (three terminals):

```bash
# Terminal 1
PROXY_LOCAL_RISK=1 \
PROXY_PORT=8000 \
PROXY_UPSTREAM_VERIFY_URL=https://x402.org/facilitator/verify \
PROXY_UPSTREAM_SETTLE_URL=https://x402.org/facilitator/settle \
uv run python run_facilitator_proxy.py

# Terminal 2
PROXY_BASE=http://localhost:8000/x402 \
uv run uvicorn --app-dir packages/x402-secure/examples seller_integration:app --port 8010

# Terminal 3
AGENT_GATEWAY_URL=http://localhost:8000 \
SELLER_BASE_URL=http://localhost:8010 \
BUYER_PRIVATE_KEY=0x6156dbafdf508898b11697a5a7af8dd7a5b7ca35841f598a6c68ac6dd3e50555 \
uv run python packages/x402-secure/examples/buyer_agent_openai.py
```

Notes:

* `PUBLIC_URL` builds `paymentRequirements.resource`.
* The proxy forwards `/x402/{verify,settle}` upstream via `PROXY_UPSTREAM_*`.
* The buyer uses `AGENT_GATEWAY_URL` (default `http://localhost:8000`) for Risk APIs.

### Signed X-PAYMENT (Default)

The buyer demo uses the official x402 SDK to create and sign **EIP-3009 TransferWithAuthorization** payloads.

**Environment variables:**

* `BUYER_PRIVATE_KEY=0x...` (Base Sepolia test key with funds)
* `NETWORK=base-sepolia`
* `AGENT_GATEWAY_URL=http://localhost:8000`
* `PROXY_UPSTREAM_VERIFY_URL=https://x402.org/facilitator/verify`
* `PROXY_UPSTREAM_SETTLE_URL=https://x402.org/facilitator/settle`
* `MERCHANT_PAYTO=0x...` (your merchant account on Base Sepolia)

**Run sequence:**

1. Start proxy
2. Start seller at port 8010
3. Run buyer demo

Notes:

* The proxy does not add upstream auth headers by default. If your target facilitator needs auth, add it at the upstream or contact us to wire optional headers.
* The `PaymentRequirements.asset` must match the network’s USDC and `payTo` must be your merchant address; the seller demo sets both.

### Using the Client SDK

**Installation**

```bash
uv lock && uv sync
```

Installs:

* `x402-secure` (client SDK)
* `x402_proxy` (proxy server module)

**SDK Components**

**AI Agent Trace Collection**

```python
from x402_client import OpenAITraceCollector, store_agent_trace

tracer = OpenAITraceCollector()
# ... collect OpenAI traces
tid = await store_agent_trace(risk_client, sid, tracer.events)
```

**Risk Session Management**

```python
from x402_client import RiskClient

risk_client = RiskClient("http://localhost:8000")
session = await risk_client.create_session(
    agent_did=buyer_address,  # Future: EIP-8004 DID
    app_id="my-app",
    device={"ua": "x402-agent/1.0"}
)
sid = session["sid"]
```

**Secure Payment Headers**

```python
from x402_client import build_payment_secure_header, start_client_span

with start_client_span("buyer.payment"):
    headers = build_payment_secure_header(agent_trace_context={"tid": tid})
```

**Complete Payment Flow**

```python
from x402_client import BuyerClient, BuyerConfig

buyer = BuyerClient(BuyerConfig(
    seller_base_url="http://localhost:8010",
    agent_gateway_url="http://localhost:8000",
    network="base-sepolia",
    buyer_private_key=os.getenv("BUYER_PRIVATE_KEY")
))
result = await buyer.execute_paid_request(
    endpoint="/api/market-data",
    task="Buy BTC price data",
    params={"symbol": "BTC/USD"},
    risk_sid=sid,
    extra_headers=headers
)
```

**Proxy Server (FastAPI)**

```python
from fastapi import FastAPI
from x402_proxy import router, risk_router

app = FastAPI()
app.include_router(router)
app.include_router(risk_router)

@app.get("/api/protected")
async def protected_resource(request: Request):
    # Verify X-PAYMENT, X-PAYMENT-SECURE, X-RISK-SESSION
    # Call /x402/verify and /x402/settle
    pass
```

See `run_facilitator_proxy.py` for a complete standalone proxy server example.

