---
title: '[tPortal] Get total balance for all agents in a project'
excerpt: |-
  Get the total balance (in USD) for all agents under a specific project.
      
      This endpoint is specifically designed for web management interface and requires:
      - User authentication via access token
      - User must have access to the specified project
      
      The endpoint will:
      - Calculate total balance in USD for all agents
      - Count total number of agents
      - Return detailed breakdown by asset type
api:
  file: openapi.json
  operationId: Balances-get_project_balances
hidden: true
---