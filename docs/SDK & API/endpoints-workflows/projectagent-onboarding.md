---
title: project/agent onboarding
deprecated: false
hidden: false
metadata:
  robots: index
---
This guide provides an overview of how projects and agents are onboarded into our system. The process is designed to be secure, flexible, and developer-friendly.

<br />

> Project onboarding should be only available through the tPortal. While agent onboarding should be only available through the tPay SDK or tLedger API.

<br />

## Project Onboarding

When a user first joins our platform, they need to create a project to manage their agents and transactions. A project serves as a container for multiple agents and provides a way to manage API access and permissions. The project creation process is straightforward - users provide a name and description, and the system automatically sets up the necessary infrastructure.

Here's a simple example of how to create a project:

```python
project = {
    "name": "My Trading Project",
    "description": "A project for managing trading agents",
    "daily_limit": 1000.0
}
```

After project creation, you must explicitly request an API key pair through the generate-api-key endpoint. This is a crucial security step as the API secret will only be shown once during generation. If you lose the API secret, you'll need to generate a new key pair.

```python
api_key_request = {
    "scopes": ["agent:profile:create", "agent:profile:read", "agent:profile:delete"],
    "resource_id": "proj_123"  # Your project ID
}
```

<br />

## Security Considerations

The security of your API credentials is of utmost importance. If your project's API key is compromised, all agents within that project could be at risk. Our system implements a comprehensive security framework that includes one-time API secret generation, continuous transaction monitoring, and automatic risk assessment. Any suspicious activities detected by our risk control system will impact both your KYC level and your agents' KYA level, potentially leading to immediate project suspension.

<br />

## Agent Onboarding and User Authorization

Agents are the core operational units within a project. Each agent represents an autonomous entity that can perform specific tasks, such as trading or payment processing. The agent onboarding process involves creating an agent profile and assigning it specific capabilities and limits.

When creating an agent, you'll need to specify its type, name, and operational parameters. The system automatically creates the necessary accounts and assigns default permissions based on the agent type.

Example agent creation:

```python
agent = {
    "name": "Trading Agent Alpha",
    "project_id": "proj_123",
    "description": "Autonomous trading agent for market operations",
    "agent_daily_limit": 100.0,
    "agent_type": "autonomous_agent"
}
```

<br />

## User Authorization and Fund Control \[wip]

*A critical aspect of our system is that agents can only operate with funds that have been explicitly authorized by the human user who created them. This fundamental security principle ensures that even with valid API credentials, no operations can be performed without explicit user authorization. The user must approve the use of their funds for each agent, and this authorization cannot be bypassed by any party, including tLedger. Users maintain full control over their funds and can revoke authorization at any time.*

<br />

## Integration Flow

The integration process begins with project creation, followed by the generation and secure storage of API credentials. Once these are in place, you can create agents within the project. Before any agent can operate, you must obtain user authorization for fund usage. After authorization is granted, you can configure agent-specific parameters and limits, and implement the necessary API calls in your application.

The system provides detailed API responses that include all necessary information for tracking and managing your agents. Each agent is assigned a unique identifier that you'll use for all subsequent operations.

<br />

## Best Practices

When implementing the onboarding process in your application, it's essential to implement proper error handling and retry mechanisms. The system provides detailed error messages that can help you identify and resolve issues quickly. Always store API credentials securely and never expose them in client-side code. Regular monitoring of agent activities and keeping KYC information up to date are crucial for maintaining a secure and compliant operation.

<br />

## Example Response Structure

When creating a project or agent, you'll receive a response that includes all necessary identifiers and configuration details:

```json
{
    "id": "proj_123",
    "name": "My Trading Project",
    "created_at": "2024-03-20T10:00:00Z"
}
```

When generating an API key pair, you'll receive a one-time response:

```json
{
    "api_key": "ak_xxx",
    "api_secret": "as_xxx",
    "scopes": "...",
}
```

<br />

This documentation provides a high-level overview of the onboarding process. For specific API endpoints and detailed parameters, please refer to our API documentation.