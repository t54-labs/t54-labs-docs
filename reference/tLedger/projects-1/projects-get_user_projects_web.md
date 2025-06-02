---
title: '[tPortal] Get all projects for current user'
excerpt: |-
  Get a list of all projects owned by the current user.
      
      This endpoint is specifically designed for web management interface and requires:
      - User authentication via access token
      
      Features:
      - Returns all active projects for the current user
      - Includes project details and associated treasury agent
api:
  file: openapi.json
  operationId: Projects-get_user_projects_web
hidden: false
---