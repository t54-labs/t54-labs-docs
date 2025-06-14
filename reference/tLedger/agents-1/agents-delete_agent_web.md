---
title: '[tPortal] Delete an agent from web management'
excerpt: |-
  Delete an agent through web management interface.
      
      This endpoint is specifically designed for web management interface and requires:
      - User authentication via access token
      - User must have access to the project that owns the agent
      - Agent must not have any non-zero balance in any asset account
      
      The deletion will fail if:
      - The agent has any non-zero balance in any asset account
      - The user doesn't have access to the project
      - The agent doesn't exist
api:
  file: openapi.json
  operationId: Agents-delete_agent_web
hidden: true
---