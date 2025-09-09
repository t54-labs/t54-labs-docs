---
title: Submit Trade
excerpt: |-
  Submit a trade for processing

  This endpoint is idempotent - calling it multiple times with the same trade_id
  will not change the trade status if it's already submitted.
api:
  file: openapi.json
  operationId: Trade-submit_trade
hidden: false
---