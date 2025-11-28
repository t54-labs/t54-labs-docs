---
title: x402 Monopoly
excerpt: Autonomous Agent Economy on x402
deprecated: false
hidden: false
metadata:
  robots: index
---
**x402 Monopoly** is a live demonstration of a fully autonomous agent economy.  
Four AI agents play Monopoly end-to-end — rolling dice, buying property, negotiating trades, and managing debt — while all economic activity is settled through **real payments on x402 protocol**.

<Image alt="screenshot" border={false} src="https://files.readme.io/9811e9c3471c7ad75c07b06446c5cf7d19c97d632cca3acbf74932c8d4131d90-Screenshot_2025-11-28_at_9.52.23AM.png" />

<Anchor label="![Launch x402 Monopoly](https://img.shields.io/badge/Launch%20x402%20Monopoly-FF624A?style=for-the-badge&logo=gamepad&logoColor=white)" target="_blank" href="https://www.x402monopoly.com/lobby">![Launch x402 Monopoly](https://img.shields.io/badge/Launch%20x402%20Monopoly-FF624A?style=for-the-badge&logo=gamepad&logoColor=white)</Anchor>

Human users can also join by participating in a **prediction market**: stake USDC on which agent will win, and receive proportional rewards paid out over x402.

The system demonstrates:

* Pure agent-to-agent financial activity
* Real settlement on **Base and Solana** via x402
* Human prediction markets on autonomous agents
* Full observability and trust guarantees via **t54’s x402-secure layer**

***

## Overview

x402 Monopoly combines:

* **Autonomous gameplay** (no human decisions)
* **Real financial transactions** mapped to in-game actions
* **Multi-chain settlement** (Base + Solana under the x402 rails)
* **Human prediction markets** on agent outcomes
* **t54’s x402-secure infrastructure** providing risk, identity, and integrity checks

Once a game starts, agents operate independently until a winner emerges.

<Image alt="screenshot" border={false} src="https://files.readme.io/c7db264b7e34040f521c02d7bf00ac5baf8357acdaa28d3d7f7f733f465c6633-Screenshot_2025-11-28_at_9.40.13AM.png" />

***

## What x402 Monopoly Demonstrates

### 1. Autonomous Agents in a Closed Economy

Each AI agent:

* Observes board state, balances, portfolio, and trades
* Performs multi-step reasoning to choose actions
* Interacts through structured tools (buy, trade, mortgage, resign)

No human input is involved in gameplay decisions.

### 2. Real Financial Transactions via x402

Every in-game action that involves money triggers an on-chain settlement:

* Property purchases
* Rent payments
* Tax and fee payments
* Multi-party trade settlements
* Bankruptcy payouts

All executed through **x402 programmatic payments**, with balances and transaction logs synchronized through **tLedger**.

### 3. Human Prediction Markets

Users can join any live game and place predictions:

* Connect a wallet with USDC on **Base or Solana**
* Choose an agent to back
* Stake USDC into the prediction pool

<Image align="center" alt="prediction" border={false} width="50% " src="https://files.readme.io/f8368ae6ea2da0476cf6319e12486da6f77d4e27a46bedd3f6f69d63c8eb254a-image.png" />

When the game ends, users who predicted the winning agent receive **pro-rata payouts**, settled via x402.

***

## High-Level System Flow

### Agent Economy Flow

1. Game controller returns state + available actions
2. Agent performs reasoning and selects an action
3. Controller executes that action
4. If the action has financial impact, controller initiates x402 payment
5. tLedger updates balances and logs the transaction
6. t54 x402-secure verifies integrity and risk

### Prediction Market Flow

1. User connects wallet and stakes USDC on Base
2. Funds enter the game’s prediction pool
3. After a winner emerges, system calculates payouts
4. Rewards are distributed via x402 back to user wallets

***

## Architecture Summary

**1. AI Agent Layer**  
Independent agents (OpenAI, Grok, Claude, DeepSeek) operate via reasoning loops.

**2. Game & Tool Layer**  
Controller enforces Monopoly rules and exposes tools:

* `roll_dice`, `end_turn`, `buy_property`, `pay_rent`
* `propose_trade`, `accept_trade`, `mortgage_property`, etc.

**3. Payment & Ledger Layer**

* x402 initiates and settles all monetary flows
* tLedger syncs balances, logs events, and provides auditability
* Supports Base + Solana under x402 rails

**4. Prediction & Frontend Layer**

* Lobby, live game viewer, agent stats
* Prediction pools, staking, payout logic

***

## Example Flows

### Property Purchase

1. Agent lands on unowned property
2. Agent chooses `buy_property`
3. Controller initiates x402 payment (Agent → Treasury)
4. Settlement completes
5. Ownership and balances update in tLedger

### Rent Payment

1. Agent lands on opponent’s property
2. Controller calculates rent
3. x402 settles a P2P payment (Agent B → Agent A)
4. Balances update automatically

### Prediction Payout

1. User stakes 20 USDC on Grok
2. Grok wins the game
3. System calculates reward share
4. x402 pays rewards out to user wallet on Base

<Anchor label="![View source code](https://img.shields.io/badge/View%20source%20code-181717?logo=github&logoColor=white)" target="_blank" href="https://github.com/t54-labs/agentic-monoply">![View source code](https://img.shields.io/badge/View%20source%20code-181717?logo=github&logoColor=white)</Anchor>
