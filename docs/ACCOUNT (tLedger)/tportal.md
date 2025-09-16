---
title: tPortal
excerpt: The user interface to interact with tLedger
deprecated: false
hidden: false
metadata:
  robots: index
---
## Description

<br />

tPortal is a comprehensive user interface (UI) designed to empower agent developers with complete control over their accounts and projects within the **tLedger** backend system.

As the native account management portal for tLedger, tPortal provides a centralized and intuitive platform for a range of critical functions, including:

**Project and Account Management**: Easily create, manage, and organize multiple projects and their associated agent accounts.

**Transaction History**: Gain full visibility into all transaction data with detailed, searchable history.

**Risk Profile Monitoring**: Proactively monitor and assess risk profiles to ensure operational security and compliance.

**Security Configuration**: Configure and manage security settings to protect agent accounts and sensitive data.

**Treasury Management**: Oversee and manage financial operations, including funds transfers, balances, and reporting. The portal also allows for direct **deposits and withdrawals** to and from agent accounts to fund them as needed.

tPortal streamlines the administration process, offering a powerful, efficient, and secure solution for managing agent operations on the tLedger platform.

<br />

![](https://files.readme.io/8027049ffec2186f36f18ddc786a3c5912fb9288edf817b682a7a445e1d58c86-image.png)

<br />

## Account Creation and Verification

To create a new account, please follow the instructions on the login page. You will be prompted to provide your email address and password. You may also provide your full name, but this is optional.

Once you have successfully created your account, a verification link will be sent to the email address you provided. To complete the setup process, please click the link to verify your email address

<Image align="center" width="60% " src="https://files.readme.io/62d09199f31e84c987741e8ef47c29e05374d40cce19efa5700f0eabc916f0cf-Screenshot_2025-09-15_at_6.44.50_PM.png" />

## Core Capabilities

### Project and Account Management

**Managing Projects**

The top-left corner of the tPortal dashboard is your control center for managing projects. You can easily switch between existing projects or create a new one to organize your agent accounts.

<Image align="center" width="100% " src="https://files.readme.io/39d64901fbadf5c57a18249de88aaea95542745a2000b5bf16352a0bba301cb4-Screenshot_2025-09-15_at_6.58.58_PM.png" />

**Switching Projects**

To switch to a different project, simply click the current project name displayed in the top-left corner. A dropdown menu will appear, showing all the projects you have access to. Select the one you wish to work in.

**Creating a New Project**

To create a new project, click "Create New Project" from the dropdown menu. A "Create New Project" window will appear, prompting you to enter the following information:

Project Name: A unique name for your project (e.g., "Treasury Project").

Project Description: A brief description to help you identify the project's purpose.

Daily Limit: Set a daily transaction limit for all agent activities within this project.

Once you have filled in the required fields, click "Create Project". The new project will be created and you will automatically be switched to its dashboard.

<br />

<Image align="center" width="100% " src="https://files.readme.io/ac1d8cedc819bee287cceddec2c356b0a8c14da9451de4642c0df004e7af8933-Screenshot_2025-09-15_at_6.59.29_PM.png" />

## Transaction History

The Transaction History section provides a chronological log of all financial movements within the system. It offers a detailed audit trail of deposits, withdrawals, and agent-specific payments.

<br />

<Image align="center" width="100% " src="https://files.readme.io/02682ae25071b91ad7565a4e48ad54638c980ddaee43783c7317d50d75e60323-Screenshot_2025-09-16_at_12.37.40_AM.png" />

**Transaction Graph**

The graph provides a visual representation of transaction volume over time.

**Currency Filter**: You can filter the graph to display data for specific cryptocurrencies (e.g., RLUSD, XRP, USDC, USDT).

**Time Axis**: The horizontal axis displays a timeline, showing transaction activity over a selected period (e.g., from mid-August to mid-September).

**Value Axis**: The vertical axis represents the monetary value of transactions in U.S. Dollars ($).

**Transaction Log**

The table below the graph lists all individual transactions. The columns provide key details for each entry.

**Timestamp**: The date and time the transaction was initiated.

**Payment ID**: A unique identifier for the transaction. This is a crucial element for tracking and referencing specific payments.

**Currency**: The specific cryptocurrency involved in the transaction (e.g., XRP).

**Network**: The blockchain network on which the transaction occurred (e.g., XRPL).

**Amount**: The quantity of the cryptocurrency transferred.

**Amount (USD)**: The U.S. Dollar value of the transaction at the time it occurred.

**Status**: The final state of the transaction.

**Sender ID**: The unique identifier of the agent or account that initiated the transaction.

## Security Configuration

The Security page is the central hub for managing API keys and defining automated payment rules for the project.

**API Key Management**

This tab allows you to create and manage API keys, which are essential for programmatic access to the system.

<Image align="center" width="100% " src="https://files.readme.io/783feb3983862ea12cba9d0ea3827a7d6849b096d16e3d08081df51acb6e2494-Screenshot_2025-09-16_at_12.41.40_AM.png" />

<br />

**Payment Rules**

This tab allows you to define and manage rules for automated payments. Click the "Create Payment Rule" button to define a new automated payment schedule.

<br />

<Image align="center" width="100% " src="https://files.readme.io/942492ac2ae0bfe9e8d71ea957e4e9bb5718362c619bc9562fb8d26fd0c63ac1-Screenshot_2025-09-16_at_12.41.55_AM.png" />

## Treasury Management

The Balances page provides a comprehensive view of all financial assets held within the treasury and by individual agents. It's designed to give users a clear, real-time snapshot of their cryptocurrency holdings and transaction history.

<br />

<Image align="center" width="100% " src="https://files.readme.io/3a5725daa8c07228558a3731b253bbce59663401f781b1ce9f9325d184337715-Screenshot_2025-09-15_at_7.10.59_PM.png" />

**Treasury Balance**

This section displays the total value of all assets in the main project wallet.

**Total USD Value**: The current aggregated value of all treasury assets is shown in U.S. Dollars ($).

**Asset Breakdown**: A detailed breakdown of each cryptocurrency asset is provided, including the coin (e.g., SOL, XRP), its current balance, and its corresponding USD value.

**Actions**: You can deposit or withdraw assets from the treasury. A toggle switch allows you to show underlying accounts to reveal the specific wallet addresses and account IDs that make up the total treasury balance

<br />

**Agents Total Balance**

This section provides an overview of the total value of assets held by all agents associated with the project.

**Total USD Value**: The aggregated value of all assets held by all agents, displayed in U.S. Dollars ($).

**Toggle**: A toggle switch allows you to display a detailed list of all agent accounts and their individual balances.

**Overview**

The detailed table provides a granular look at each agent's holdings and the specific asset accounts they manage.

**Agent Name**: The user-defined name for the agent.

**Agent ID**: A unique identifier for the agent.

**Daily Limit (USD)**: The maximum U.S. Dollar value of transactions the agent can perform in a 24-hour period.

**Balance (USD)**: The total U.S. Dollar value of assets currently held by the agent.

**Last Edit**: The date of the most recent activity on the account.
