---
title: Get Transaction History
excerpt: |-
  Get transaction history for a virtual asset account.

  Args:
      asset_account_id: The ID of the asset account
      db: Database session
      current_user: Auth Token for authentication
      
  Returns:
      List of transactions with details including:
      - Transaction ID
      - Amount
      - Type (CREDIT/DEBIT)
      - Timestamp
      - Transaction hash
      - Running balance
      - From asset account ID
      - To asset account ID
api:
  file: openapi.json
  operationId: Virtual Account-get_transaction_history
hidden: false
---