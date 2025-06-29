---
title: Get Agent Asset Balance
excerpt: |-
  Get the balance for a specific asset on a specific network for an agent.

  Returns 0 if the asset account doesn't exist.

  Args:
      session: Database session
      agent_id: The ID of the agent
      network: The network (e.g., solana, xrpl)
      asset: The asset type (e.g., USDC, XRP, SOL)
      api_key: API key for authentication
      secret: API secret for authentication
      request: FastAPI request object for rate limiting

  Returns:
      AssetBalanceResponse: The balance information for the specific asset
api:
  file: openapi.json
  operationId: Balances-get_agent_asset_balance
hidden: false
---