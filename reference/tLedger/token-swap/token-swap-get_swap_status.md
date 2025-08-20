---
title: Get Swap Status
excerpt: |-
  Get the status of a token swap.

  This endpoint returns the current status and details of a swap, including:
  - Current status (pending, processing, completed, failed, cancelled)
  - Transaction hash (when available)
  - Actual output amount (when completed)
  - Fees
  - Error details (if failed)

  **Authentication Required**: Either API key/secret or Bearer token
  **Rate Limited**: Subject to API rate limiting
api:
  file: openapi.json
  operationId: Token Swap-get_swap_status
hidden: false
---