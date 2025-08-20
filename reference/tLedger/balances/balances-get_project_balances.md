---
title: '[tPortal] Get total balance for all agents in a project'
excerpt: >-
  Get the total balance (in USD) for all agents under a specific project,
  separated by treasury agent and other agents.
      
      This endpoint is specifically designed for web management interface and requires:
      - User authentication via access token
      - User must have access to the specified project
      
      The endpoint will:
      - Calculate total balance in USD for all agents
      - Count total number of agents
      - Return separate breakdowns for treasury agent and other agents
      - Provide detailed breakdown by asset type for each category
api:
  file: openapi.json
  operationId: Balances-get_project_balances
hidden: false
---