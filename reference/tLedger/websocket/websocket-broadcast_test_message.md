---
title: Broadcast Test Message
excerpt: |-
  Test broadcast message (for development and debugging only)

  Args:
      event_type: Event type
      message: Message content
      payment_id: Optional payment ID, if provided only sends to connections subscribed to this payment
api:
  file: openapi.json
  operationId: WebSocket-broadcast_test_message
hidden: false
---