---
title: Production vs Sandbox
deprecated: false
hidden: false
metadata:
  robots: index
---
t54's platform operates in two distinct environments to support your development lifecycle from testing to production deployment.

* **Sandbox**: Free testing environment
* **Production**: Live environment for your deployed agents with real blockchain operations

You can access both environments through our unified API by simply changing the base URL in your configuration.

## 🔬 Sandbox Testing Environment

If you're in the development phase and need access to an online test environment, we provide a Sandbox for safe testing:

**Sandbox Base URL:** `https://api-sandbox.t54.ai/api/v1`

In both SDK and RESTful API calls, simply set your `BASE_URL` to the above address to access the testnet/devnet-based sandbox. All networks in the sandbox are either testnet or devnet versions.

### 🎁 Test Token Airdrops

For every new Agent you create—whether a Treasury Agent under a Project or a standard Autonomous Agent—our system automatically airdrops test tokens at creation. These tokens grow in variety as our system evolves.

**Currently supported airdrops:**

* **Solana (SOL):** 0.02 SOL
* **XRPL (XRP):** 100 XRP

You can view airdrop details in the Agent's profile under details.

## Differences Between Environments

| Feature                 | Sandbox                                                             | Production                                                     |
| ----------------------- | ------------------------------------------------------------------- | -------------------------------------------------------------- |
| **Base URL**            | `https://api-sandbox.t54.ai/api/v1`                                 | `https://api.t54.ai/api/v1`                                    |
| **Cost**                | **Free** - No charges for any operations                            | **Live billing** - Real transaction costs apply                |
| **Blockchain Networks** | **Testnet/Devnet only** (Solana Devnet, XRPL Testnet, Base Sepolia) | **Mainnet** (Solana, XRPL, Base mainnet)                       |
| **Test Tokens**         | **Automatic airdrops** for new agents                               | **Real tokens required** - Must fund agents with actual assets |
| **API Keys**            | Same API keys work across both environments                         | Same API keys work across both environments                    |
| **Rate Limits**         | Relaxed limits for testing                                          | Standard production rate limits                                |
| **Data Persistence**    | **May be reset periodically**                                       | **Permanent** - Production data is never deleted               |

<br />

***

**Need help?** Check our [API documentation](/docs/api) or [contact support](/discussion) for assistance with environment setup.