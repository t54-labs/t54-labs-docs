---
title: Global Payroll
deprecated: false
hidden: false
metadata:
  robots: index
---
Automate cross-border salary payments to employee agents. Built on **tLedger** (settlement) and **Trustline** (risk), the Payroll MCP agent coordinates with each employee’s **Claire** agent through secure A2A messaging.

***

### Overview

<div style={{ display: "flex", justifyContent: "center" }}>
  <Cards columns={2} style={{ gap: 24 }}>
    <Card style={{ width: 420, minHeight: 160, margin: "0 auto" }}>
      <div align="center" style={{ fontWeight: 700 }}>Employer Side — Payroll MCP Agent</div>

      <div align="center" style={{ marginTop: 8 }}>
        Creates batches, authenticates, calculates totals, triggers payments, monitors status.
      </div>
    </Card>

    <Card style={{ width: 420, minHeight: 160, margin: "0 auto" }}>
      <div align="center" style={{ fontWeight: 700 }}>Employee Side — Claire Agent</div>

      <div align="center" style={{ marginTop: 8 }}>
        Receives A2A notifications, confirms test payment, accepts full payroll, updates balances.
      </div>
    </Card>
  </Cards>
</div>

***

### High-Level Flow

1. **Authenticate**
   Payroll MCP authenticates with t54 (API key/secret).

2. **Prepare Run**
   List employees → compute monthly total → (optional) check balance.

3. **Trigger Payroll (Per Employee)**
   * **Test payment**: send a small amount (e.g., `0.01 RLUSD`) to the employee’s Claire A2A endpoint.
   * **Confirm**: wait for Claire to acknowledge receipt.
   * **Full payment**: send the net salary (e.g., `3,000 RLUSD`) for the month.

4. **Monitor & Settle**
   Use history endpoints to track `PENDING` → `CONFIRMED` (or `FAILED` / `CANCELLED`).

5. **Employee Actions (Claire)**
   Employee views balance, history, and can **withdraw** to a wallet when desired.

> Typical runs complete in seconds once the employee agent confirms the test payment.

***

### States You’ll See

| **State**   | **Meaning**                                                                  |
| ----------- | ---------------------------------------------------------------------------- |
| `PENDING`   | Awaiting agent confirmation or network finality                              |
| `CONFIRMED` | Completed and recorded                                                       |
| `FAILED`    | Attempt failed (e.g., endpoint down)                                         |
| `CANCELLED` | Aborted by system or insufficient funds at execution time                    |
| `DE-DUPE`   | Duplicate attempt blocked while an existing payment for the period is active |

***

### Retries & Common Issues

* **Agent not responding** → test payment stays `PENDING`. Fix the employee’s **A2A endpoint** (ensure service online) or wait for timeout; then re-trigger.
* **Insufficient funds** → full payment may be `CANCELLED`. Top up RLUSD, then re-trigger the period’s payroll.
* **Network hiccups** → history checks can error while payments continue in the background; re-query later.

***

### MCP Tools Used (Summary)

| **Tool**              | **Purpose**                                                              |
| --------------------- | ------------------------------------------------------------------------ |
| `authenticate`        | Start a session with t54 payroll APIs (API key/secret required)          |
| `list_employees`      | Fetch active employees with salary configs                               |
| `check_balance`       | Confirm available RLUSD                                                  |
| `trigger_payroll`     | Run test → confirm → full payment per employee                           |
| `get_payment_history` | Poll status, detect `PENDING / CONFIRMED / FAILED / CANCELLED / DE-DUPE` |
| `add_employee`        | Onboard a new employee (Agent ID, A2A endpoint, monthly salary)          |

> **Security**: never paste API keys into chat UIs or logs. Store credentials in env/secrets. Redact in screenshots.

***

### Onboarding a New Employee (Minimal)

You’ll need: **Agent ID** (tLedger), **A2A endpoint** (employee’s Claire URL), **Monthly salary** (in `RLUSD`).

1. Call `add_employee` with those fields.
2. Verify the entry via `list_employees`.
3. Run `trigger_payroll` for the month when ready.

***

### Links

* Use **Claire** to view balances, history, and withdraw:
  [Claire Agent →](/v1.4/docs/claire)

* Connect org-side flows via MCP:
  [tLedger MCP Quickstart →](https://docs.t54.ai/v1.4/update/docs/tledger-mcp#/)

* Run x402 facilitator with Trustline headers (for A2A commerce):
  [x402-Secure Quickstart →](https://docs.t54.ai/v1.4/update/docs/x402-secure-quickstart#/)

<br />

<br />

<br />

<Image border={false} src="https://files.readme.io/e5660fa83fe0b6100b4fbe2beb3d401437c02810f174cd561ad4d3bcd82b558e-image.png" />

<br />
