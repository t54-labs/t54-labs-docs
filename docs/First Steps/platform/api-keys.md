---
title: API Keys
deprecated: false
hidden: true
metadata:
  robots: index
---
API keys are required to authorize requests against the t54 APIs. By using an API key, t54 knows which project is making the call, and can manage agent operations within your specified project scope.

## API Authentication

This page provides a high-level walkthrough of the most important tLedger API endpoints and how they map to common agent workflows. For full schema details and exhaustive endpoint documentation, please refer to the API Reference.

### Authentication Headers

All API requests must include the following headers:

```http
X-API-Key: your_api_key
X-API-Secret: your_api_secret
```

**Important Notes:**

* API keys are tied to only one project
* API scope is limited to the specified project, including all agent instances under this project
* API keys can only be generated from the [tPortal](/tPortal) manually

### Sandbox vs Production Environment

Choose the appropriate base URL for your environment:

* **Sandbox environment**: `https://api-sandbox.t54.ai/api/v1`
* **Production environment**: `https://api.t54.ai/api/v1`

For detailed information about environment differences, see our [Production vs Sandbox](/docs/production-vs-sandbox) guide.

## API Scopes

t54 API keys support granular permission scopes to ensure secure access control:

#### tPay APIs (Agent Operations)

Agent-level operations that your AI agents can perform:

* `payments:read` - View payment history and transaction details
* `payments:write` - Execute payments and transfers
* `balance:read` - Check agent account balances

#### tLedger APIs (Administrative Operations)

Project-level administrative operations for managing agents:

* `agent:profile:create` - Create new agent profiles
* `agent:profile:read` - View agent profile information
* `agent:profile:update` - Modify agent settings and configurations
* `agent:profile:delete` - Remove agent profiles
* `agent:limits:create` - Set spending limits for agents
* `agent:limits:read` - View current spending limits
* `agent:limits:update` - Modify spending limits
* `agent:account:read` - Access agent account information
* `agent:account:delete` - Delete agent accounts

***

**Need help?** Check our [API documentation](/docs/api) or [contact support](/discussion) for assistance with environment setup.