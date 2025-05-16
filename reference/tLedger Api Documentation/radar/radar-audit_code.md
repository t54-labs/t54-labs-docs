---
title: Audit Code
excerpt: >-
  Audit code quality


  This endpoint allows developers to upload multiple agent core function names
  and code,

  and the system will audit the code quality of each function using LLM and
  provide scores and feedback.


  The audit results will be saved to the database, including:

  - Function name

  - Function code

  - Code hash

  - Project ID

  - Audit score

  - Audit feedback

  - Timestamp


  Valid API Key and Secret are required to use this endpoint.
api:
  file: openapi.json
  operationId: Radar-audit_code
hidden: false
---