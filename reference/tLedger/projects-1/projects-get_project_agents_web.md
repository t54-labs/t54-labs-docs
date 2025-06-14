---
title: '[tPortal] Get agents list for a project with search, pagination and sorting'
excerpt: >-
  Get a paginated list of agents for a specific project with search, sorting and
  balance information.
      
      This endpoint is specifically designed for web management interface and requires:
      - User authentication via access token
      - User must have access to the specified project
      
      Features:
      - Search agents by name or description
      - Sort by last update time or total balance in USD
      - Pagination support
      - Balance calculation in USD for each agent
api:
  file: openapi.json
  operationId: Projects-get_project_agents_web
hidden: true
---