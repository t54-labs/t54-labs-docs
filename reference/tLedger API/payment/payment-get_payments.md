---
title: '[tPortal] Get payments list for a project'
excerpt: |-
  Retrieve a paginated list of payments for all agents under a specific project.
      
      The endpoint requires:
      - User authentication via access token
      - Project ID to filter payments
      - Optional pagination and sorting parameters
      
      Returns a paginated list of payments with metadata including:
      - Payment details (amount, status, agents, etc.)
      - Pagination information (current page, total pages, etc.)
api:
  file: openapi.json
  operationId: Payment-get_payments
hidden: false
---