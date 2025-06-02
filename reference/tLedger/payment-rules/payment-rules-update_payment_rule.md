---
title: '[tPortal] Update a payment rule'
excerpt: |-
  Update an existing payment rule.
      This endpoint is specifically designed for web management interface.

      Sample Request:
      ```json
      {
          "status": "inactive",
          "config": {
              "amount": 2000.0,
              "currency": "USD",
              "refresh_period": "daily"
          },
          "description": "Updated daily spending limit",
          "priority": 2,
          "effective_from": "2024-02-01T00:00:00Z",
          "effective_until": "2024-12-31T23:59:59Z",
          "rule_metadata": {
              "updated_by_admin": true,
              "reason": "Increased spending limit"
          }
      }
      ```

      Sample Response:
      ```json
      {
          "id": "rule_123",
          "rule_type": "spend_limit",
          "rule_level": "project",
          "status": "inactive",
          "config": {
              "amount": 2000.0,
              "currency": "USD",
              "refresh_period": "daily"
          },
          "description": "Updated daily spending limit",
          "priority": 2,
          "effective_from": "2024-02-01T00:00:00Z",
          "effective_until": "2024-12-31T23:59:59Z",
          "created_at": "2024-01-01T00:00:00Z",
          "updated_at": "2024-02-01T00:00:00Z",
          "version": 2,
          "project_id": "proj_123",
          "agent_id": null,
          "created_by": "user_123",
          "rule_metadata": {
              "updated_by_admin": true,
              "reason": "Increased spending limit"
          }
      }
      ```
api:
  file: openapi.json
  operationId: Payment Rules-update_payment_rule
hidden: false
---