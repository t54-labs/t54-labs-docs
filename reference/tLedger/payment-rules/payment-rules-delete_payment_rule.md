---
title: '[tPortal] Delete a payment rule'
excerpt: |-
  Delete a payment rule by setting its status to inactive.
      This endpoint is specifically designed for web management interface.

      Sample Response:
      ```json
      {
          "id": "rule_123",
          "rule_type": "spend_limit",
          "rule_level": "project",
          "status": "inactive",
          "config": {
              "amount": 1000.0,
              "currency": "USD",
              "refresh_period": "daily"
          },
          "description": "Project daily spending limit",
          "priority": 1,
          "effective_from": "2024-01-01T00:00:00Z",
          "effective_until": "2024-12-31T23:59:59Z",
          "created_at": "2024-01-01T00:00:00Z",
          "updated_at": "2024-02-01T00:00:00Z",
          "version": 2,
          "project_id": "proj_123",
          "agent_id": null,
          "created_by": "user_123",
          "rule_metadata": {
              "deleted_by_admin": true,
              "reason": "Rule no longer needed"
          }
      }
      ```
api:
  file: openapi.json
  operationId: Payment Rules-delete_payment_rule
hidden: false
---