---
title: '[tPortal] Create a new payment rule'
excerpt: |-
  Create a new payment rule for a project or agent.
      For spend_limit type rules, only one active rule is allowed per project/agent.
      This endpoint is specifically designed for web management interface.

      Sample Request:
      ```json
      {
          "rule_type": "spend_limit",
          "rule_level": "project",
          "config": {
              "project_id": "proj_123",
              "amount": 1000.0,
              "currency": "USD",
              "refresh_period": "daily",
              "start_time": "2024-01-01T00:00:00Z",
              "end_time": "2024-12-31T23:59:59Z"
          },
          "description": "Daily spending limit of 1000 USD",
          "priority": 1,
          "effective_from": "2024-01-01T00:00:00Z",
          "effective_until": "2024-12-31T23:59:59Z",
          "rule_metadata": {
              "created_by_admin": true,
              "approval_required": false
          }
      }
      ```

      Sample Response:
      ```json
      {
          "id": "rule_123",
          "rule_type": "spend_limit",
          "rule_level": "project",
          "status": "active",
          "config": {
              "project_id": "proj_123",
              "amount": 1000.0,
              "currency": "USD",
              "refresh_period": "daily",
              "start_time": "2024-01-01T00:00:00Z",
              "end_time": "2024-12-31T23:59:59Z"
          },
          "description": "Daily spending limit of 1000 USD",
          "priority": 1,
          "effective_from": "2024-01-01T00:00:00Z",
          "effective_until": "2024-12-31T23:59:59Z",
          "created_at": "2024-01-01T00:00:00Z",
          "updated_at": "2024-01-01T00:00:00Z",
          "version": 1,
          "project_id": "proj_123",
          "agent_id": null,
          "created_by": "user_123",
          "rule_metadata": {
              "created_by_admin": true,
              "approval_required": false
          }
      }
      ```
api:
  file: openapi.json
  operationId: Payment Rules-create_payment_rule
hidden: false
---