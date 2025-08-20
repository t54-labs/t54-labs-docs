---
title: '[tPortal] Get payments list for a specific agent'
excerpt: >-
  Retrieve a paginated list of payments where the specified agent is either the
  sender or receiver.
      
      The endpoint requires:
      - User authentication via access token
      - Agent ID to filter payments
      - Optional pagination and sorting parameters
      
      Returns a paginated list of payments with metadata including:
      - Payment details (amount, status, agents, etc.)
      - Pagination information (current page, total pages, etc.)
      
      The response includes payments where the agent is:
      - The sending agent (outgoing payments)
      - The receiving agent (incoming payments)
api:
  file: openapi.json
  operationId: Payment-get_agent_payments
hidden: false
---