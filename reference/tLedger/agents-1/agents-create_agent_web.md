---
title: '[tPortal] Create a new agent from web management'
excerpt: |-
  Create a new agent through web management interface.
      
      This endpoint is specifically designed for web management interface and requires:
      - User authentication via access token
      - User must have access to the specified project
      
      The agent will be created under the specified project and will inherit the project's settings.
api:
  file: openapi.json
  operationId: Agents-create_agent_web
hidden: true
---