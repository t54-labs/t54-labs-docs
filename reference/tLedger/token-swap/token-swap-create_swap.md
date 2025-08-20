---
title: Create Swap
excerpt: |-
  Create a simple token swap.

  This endpoint initiates a token swap with minimal required parameters:
  - asset_account_id: The asset account to swap from
  - to_token: The token to swap to
  - amount: The amount to swap

  The from_token is automatically determined from the asset account.

  **Authentication Required**: Either API key/secret or Bearer token
  **Rate Limited**: Subject to API rate limiting
api:
  file: openapi.json
  operationId: Token Swap-create_swap
hidden: false
---