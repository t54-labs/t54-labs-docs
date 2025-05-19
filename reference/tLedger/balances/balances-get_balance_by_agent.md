---
title: Get Balance By Agent
excerpt: >-
  Get the total balance for an agent, converted to USD.

  If the agent has multiple asset accounts, returns the sum of all balances in
  USD.


  Args:
      session: Database session
      agent_id: The ID of the agent
      api_key: API key for authentication
      secret: API secret for authentication
      request: FastAPI request object for rate limiting

  Returns:
      AgentBalanceResponse: The total balance in USD and breakdown by asset
api:
  file: openapi.json
  operationId: Balances-get_balance_by_agent
hidden: false
---