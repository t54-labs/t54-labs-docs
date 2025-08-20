---
title: Get all asset accounts for an agent
excerpt: |-
  Retrieve all asset accounts owned by a specific agent.
      
      This endpoint returns comprehensive information about each asset account including:
      - Account ID for reference
      - Wallet address for deposits/withdrawals
      - Currency/Asset type (e.g., SOL, USDC, XRP)
      - Network information (e.g., Solana, XRPL)
      - Testnet flag to distinguish test vs production accounts
      - Account metadata containing additional configuration
     
      **Authentication Required**: Either API key/secret (X-API-Key/X-API-Secret headers) or Bearer token (Authorization header).
      **Rate Limited**: Subject to API rate limiting (60 requests per minute).
api:
  file: openapi.json
  operationId: Virtual Account-get_agent_asset_accounts
hidden: false
---