---
title: tLedger Toolkit
excerpt: Toolkit for integrating tLedger APIs into AI agent frameworks.
deprecated: false
hidden: false
metadata:
  robots: index
---
The **tLedger Agent Toolkit** enables seamless integration with tLedger APIs, allowing agents to initiate and manage Agent-to-Agent payments. It is designed to work with popular AI agent frameworks such as Virtual's GAME SDK and ai16z’s Eliza.

# Installation

Install the toolkit via pip:

```bash
pip install tledger-agent-toolkit
```

## Requirements

* Python 3.11+

# Usage

Configure **tLedger Agent Toolkit** using your TLedger API credentials and integrate it into your AI agent environment.

```python
from agents import Agent
from tledger_agent_toolkit import TLedgerAgentToolkit

# Initialize TLedger toolkit
tledger_agent_toolkit = TLedgerAgentToolkit(
    api_key="your_api_key",
    api_secret="your_api_secret",
    configuration={
        "actions": {
            "payment": {
                "create": True
            }
        }
    }
)

# Use it in an AI agent
tledger_agent = Agent(
    name="TLedger Agent",
    instructions="You are an expert at interacting with TLedger APIs for payments.",
    tools=tledger_agent_toolkit.get_tools()
)
```

## Features

* **Payment API Support**: Initiate and manage payments via tLedger API.
* **Easy Integration**: Plug-and-play support for top AI agent frameworks.
* **Customizable Actions**: Configure which tLedger actions agents can perform