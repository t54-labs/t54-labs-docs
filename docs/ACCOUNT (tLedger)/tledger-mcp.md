---
title: tLedger MCP
excerpt: >-
  A Model Context Protocol (MCP) server that provides tools for interacting with
  the t54 Payment Gateway API
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

This MCP server enables Claude and other MCP-compatible clients to interact with the t54 Payment Gateway API, allowing for payment processing, agent management, and balance queries.

## Features

* **Payment Management**: Create and retrieve payment transactions, list all payments with filtering and pagination
* **Agent Profiles**: Get detailed agent information, onboard new agents, and manage agent limits
* **Balance Queries**: Check agent balances across all assets or specific asset/network combinations
* **Project Management**: List all agents associated with a project, get detailed project information
* **Account Management**: Retrieve detailed account information by account ID
* **Virtual Account Management**: Create and track withdrawal requests from virtual accounts

## Available Tools

### 1. `create_payment`

Creates a new payment transaction between two agents.

**Parameters:**

* `sending_agent_id` (required): ID of the agent sending the payment
* `receiving_agent_id` (required): ID of the agent receiving the payment
* `payment_amount` (required): Payment amount (must be positive)
* `currency` (required): Currency type (e.g., USDC, USDT, SOL)
* `request_id` (optional): Unique ID for idempotency
* `settlement_network` (optional): Network for settlement (default: "solana")
* `trace_context` (optional): JSON string with runtime context
* `func_stack_hashes` (optional): JSON array of function hashes
* `debug_mode` (optional): Enable offline processing

**Note:** API credentials are configured via environment variables (see Configuration section).

### 2. `get_payment_details`

Retrieves details of a specific payment transaction.

**Parameters:**

* `payment_id` (required): Unique ID of the payment

### 3. `get_payments_list`

Retrieves a list of all payments with optional filtering and pagination.

**Parameters:**

* `project_id` (required): ID of the project to get payments for
* `page_number` (optional): Page number for pagination (default: 1)
* `page_size` (optional): Number of payments per page (default: 10)
* `sort_by` (optional): Field to sort by (default: 'created_at')
* `order` (optional): Sort order: 'asc' or 'desc' (default: 'desc')
* `status` (optional): Filter by payment status (e.g., 'completed', 'pending', 'failed')
* `sending_agent_id` (optional): Filter by sending agent ID
* `receiving_agent_id` (optional): Filter by receiving agent ID

### 4. `get_agent_profile`

Retrieves detailed information about a specific agent including account details.

**Parameters:**

* `agent_id` (required): Unique ID of the agent

### 5. `onboard_agent`

Onboards a new agent to the t54 platform.

**Parameters:**

* `project_id` (required): ID of the project this agent belongs to
* `name` (required): Name of the agent
* `agent_description` (required): Description of the agent's purpose
* `agent_type` (required): Type of agent (e.g., 'user', 'system', 'bot')
* `daily_limit` (required): Daily spending limit for the agent

### 6. `get_agent_limits`

Retrieves the daily limit configuration for a specific agent.

**Parameters:**

* `agent_id` (required): Unique ID of the agent

### 7. `get_agent_balance`

Retrieves the total balance for an agent across all assets, converted to USD.

**Parameters:**

* `agent_id` (required): Unique ID of the agent

### 8. `get_agent_asset_balance`

Retrieves the balance for a specific asset on a specific network for an agent.

**Parameters:**

* `agent_id` (required): Unique ID of the agent
* `network` (required): Network name (e.g., solana, xrpl, evm_base)
* `asset` (required): Asset type (e.g., USDC, SOL, XRP)

### 9. `get_project_agents`

Retrieves a list of all agents associated with a specific project.

**Parameters:**

* `project_id` (required): Unique ID of the project

### 10. `get_account_details`

Retrieves detailed information about a specific account by account ID.

**Parameters:**

* `account_id` (required): Unique ID of the account

### 11. `create_virtual_account_withdrawal`

Creates a withdrawal request from a virtual account.

**Parameters:**

* `account_id` (required): ID of the virtual account to withdraw from
* `amount` (required): Amount to withdraw (must be positive)
* `currency` (required): Currency to withdraw (e.g., USDC, USDT, SOL)
* `destination_address` (required): Destination wallet address
* `destination_network` (required): Destination network (e.g., solana, ethereum)
* `request_id` (optional): Unique ID for idempotency. Auto-generated if not provided
* `metadata` (optional): Additional metadata for the withdrawal

### 12. `get_virtual_account_withdrawal`

Retrieves details of a specific virtual account withdrawal request.

**Parameters:**

* `request_id` (required): Unique ID of the withdrawal request

## Installation

1. Clone this repository or download the files
2. Install dependencies using uv:
   ```bash
   uv add "mcp[cli]" httpx pydantic python-dotenv
   ```

## Configuration

The server uses environment variables for API credentials. You can configure these in several ways:

### Option 1: Environment Variables

Set the following environment variables:

```bash
export T54_API_KEY="your-api-key"
export T54_API_SECRET="your-api-secret"
export T54_BASE_URL="<T54_SERVER_ENDPOINT>"  # Optional, defaults to production
```

### Option 2: .env File

Create a `.env` file in the project directory:

```
T54_API_KEY=your-api-key
T54_API_SECRET=your-api-secret
T54_BASE_URL=https://api.t54.app/api/v1
```

**Important:** Never commit your `.env` file to version control. Add it to `.gitignore`.

### Option 3: Claude Desktop Configuration

Configure environment variables directly in Claude Desktop (see Claude Desktop Integration section).

## Running the Server

### For Development/Testing

Use the MCP Inspector to test the server:

```bash
uv run mcp dev t54_server.py
```

This opens an interactive web UI where you can test each tool.

### For Production

Run the server directly:

```bash
uv run t54_server.py
```

## Claude Desktop Integration

To use this server with Claude Desktop:

1. Find your Claude Desktop configuration file:
   * **macOS**: `~/Library/Application\ Support/Claude/claude_desktop_config.json`
   * **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

2. Add the server configuration:

```json
{
  "mcpServers": {
    "t54": {
      "command": "uv",
      "args": [
        "--directory",
        "/absolute/path/to/t54-mcp",
        "run",
        "t54_server.py"
      ],
      "env": {
        "T54_API_KEY": "your-api-key",
        "T54_API_SECRET": "your-api-secret",
        "T54_BASE_URL": "https://api.t54.app/api/v1"
      }
    }
  }
}
```

3. Replace `/absolute/path/to/t54-mcp` with the actual absolute path to this directory
4. Replace `your-api-key` and `your-api-secret` with your actual t54 API credentials
5. Restart Claude Desktop
6. You could also drag the t54 dxt file into the Claude Desktop window to add it automatically.

<Image align="center" src="https://files.readme.io/346eafdd3ce706b0bc3e04d862870d809055f40e030a5611ac6f4ea30bc3e9d6-Screenshot_2025-08-12_at_8.21.46_PM.png" />

<Image align="center" src="https://files.readme.io/020ffbd0c0e8116fefe16081f8f508a61ae793db9021d86be2952cfec119d4bd-Screenshot_2025-08-12_at_8.22.06_PM.png" />

## API Configuration

By default, the server connects to the production t54 API at `https://api.t54.app/api/v1`.

For local testing, you can modify the `BASE_URL` in `t54_server.py`:

```python
BASE_URL = "http://localhost:4000/api/v1"
```

## Security

* API credentials are configured via environment variables, not passed as parameters
* Credentials are loaded once at startup and not stored permanently
* All API requests use HTTPS by default
* API keys should be kept secure and not shared
* Never commit `.env` files or API credentials to version control
* Use environment-specific credentials for different deployments

## Error Handling

The server includes comprehensive error handling:

* HTTP errors are caught and returned with status codes
* Connection errors are handled gracefully
* Invalid parameters are validated using Pydantic models
* Error responses include detailed error messages

## License

This project is provided as-is for use with the t54 Payment Gateway API.