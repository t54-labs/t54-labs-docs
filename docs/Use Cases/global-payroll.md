---
title: Global Payroll
deprecated: false
hidden: false
metadata:
  robots: index
---
automate cross-border salary payments to employee agents. built on **tledger** (settlement) and **trustline** (risk), the payroll mcp agent coordinates with each employee’s **claire** agent through secure a2a messaging.

***

### overview

<Cards columns={2}>
  <Card>
    <div align="center" style={{ fontWeight: 700 }}>employer side — payroll mcp agent</div>
    <div align="center">creates batches, authenticates, calculates totals, triggers payments, monitors status.</div>
  </Card>

  <Card>
    <div align="center" style={{ fontWeight: 700 }}>employee side — claire agent</div>
    <div align="center">receives a2a notifications, confirms test payment, accepts full payroll, updates balances.</div>
  </Card>
</Cards>

***

### high-level flow

1. **authenticate**
   payroll mcp authenticates with t54 (api key/secret).
2. **prepare run**
   list employees → compute monthly total → (optional) check balance.
3. **trigger payroll (per employee)**
   * **test payment**: send a small amount (e.g., `0.01 RLUSD`) to the employee’s claire a2a endpoint.
   * **confirm**: wait for claire to acknowledge receipt.
   * **full payment**: send the net salary (e.g., `3,000 RLUSD`) for the month.
4. **monitor & settle**
   use history endpoints to track `PENDING` → `CONFIRMED` (or `FAILED/CANCELLED`).
5. **employee actions (claire)**
   employee views balance, history, and can **withdraw** to a wallet when desired.

> normal runs complete in ~seconds once the employee agent confirms the test payment.

***

### states you’ll see

| state       | meaning                                                                 |
| ----------- | ----------------------------------------------------------------------- |
| `PENDING`   | awaiting agent confirmation or network finality                         |
| `CONFIRMED` | completed and recorded                                                  |
| `FAILED`    | attempt failed (e.g., endpoint down)                                    |
| `CANCELLED` | aborted by system or insufficient funds at time of execution            |
| de-dupe     | system prevents duplicate payroll attempts while one is still `PENDING` |

***

### retries & common issues

* **agent not responding**: test payment stays `PENDING`. fix the employee’s **a2a endpoint** (ensure service is online) or wait for timeout; then re-trigger.
* **insufficient funds**: full payment may be `CANCELLED`. top up RLUSD, then retrigger the same month’s payroll.
* **network hiccups**: history checks can error while payments continue in the background; re-query later.

***

### mcp tools used (summary)

| tool                  | what it does (no pii)                                            |
| --------------------- | ---------------------------------------------------------------- |
| `authenticate`        | start a session with t54 payroll apis (api key/secret required). |
| `list_employees`      | fetch active employees with salary configs.                      |
| `check_balance`       | confirm available RLUSD.                                         |
| `trigger_payroll`     | run test → confirm → full payment per employee.                  |
| `get_payment_history` | poll status, detect `pending/confirmed/failed/cancelled`.        |
| `add_employee`        | onboard a new employee (agent id, a2a endpoint, monthly salary). |

> **security**: never paste api keys into chat or ui fields that are logged. store credentials in env/secrets (vault/ci). redact in screenshots/logs.

***

### onboarding a new employee (minimal)

you’ll need:

* **agent id** (from tledger)
* **a2a endpoint** (employee’s claire http endpoint)
* **monthly salary** (in `RLUSD`)

steps:

1. call `add_employee` with the three fields.
2. verify the new entry appears in `list_employees`.
3. run `trigger_payroll` for the current month when ready.

***

### example run (anonymized)

* employer authenticates → lists **5** employees → total **~18k RLUSD**
* triggers payroll: 4 employees **confirmed** end-to-end within ~1 minute
* 1 employee stuck at **test `PENDING`** (endpoint issue) → later **confirmed**, then **full payment** processed
* new employee added (agent id + a2a + salary). first attempts **failed** (endpoint OK, but balance low), then **top-up** → full payment **initiated** and **confirmed**

***

### links

* use **claire** to view balances, history, and withdraw:
  [claire agent page →](/v1.4/docs/claire)
* set up org-side flows or connect via mcp:
  [tledger mcp quickstart →](https://docs.t54.ai/v1.4/update/docs/tledger-mcp#/)
* run x402 facilitator with trustline headers (for a2a commerce):
  [x402-secure quickstart →](https://docs.t54.ai/v1.4/update/docs/x402-secure-quickstart#/)
