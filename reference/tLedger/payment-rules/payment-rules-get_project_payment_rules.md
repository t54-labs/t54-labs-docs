---
title: '[tPortal] Get all payment rules for a project'
excerpt: |-
  Get all payment rules for a specific project, including project-level rules
      and rules for all agents under the project.
      This endpoint is specifically designed for web management interface.

      Query Parameters:
      - rule_type: Filter rules by type (e.g., "spend_limit")
      - status: Filter rules by status (e.g., "active", "inactive", "pending")

      Sample Response:
      ```json
      {
          "project_rules": [
              {
                  "id": "rule_123",
                  "rule_type": "spend_limit",
                  "rule_level": "project",
                  "status": "active",
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
                  "updated_at": "2024-01-01T00:00:00Z",
                  "version": 1,
                  "project_id": "proj_123",
                  "agent_id": null,
                  "created_by": "user_123",
                  "rule_metadata": {}
              }
          ],
          "agent_rules": [
              {
                  "id": "rule_456",
                  "rule_type": "spend_limit",
                  "rule_level": "agent",
                  "status": "active",
                  "config": {
                      "amount": 500.0,
                      "currency": "USD",
                      "refresh_period": "daily"
                  },
                  "description": "Agent daily spending limit",
                  "priority": 2,
                  "effective_from": "2024-01-01T00:00:00Z",
                  "effective_until": "2024-12-31T23:59:59Z",
                  "created_at": "2024-01-01T00:00:00Z",
                  "updated_at": "2024-01-01T00:00:00Z",
                  "version": 1,
                  "project_id": null,
                  "agent_id": "agent_123",
                  "created_by": "user_123",
                  "rule_metadata": {}
              }
          ]
      }
      ```
api:
  file: openapi.json
  operationId: Payment Rules-get_project_payment_rules
hidden: false
---