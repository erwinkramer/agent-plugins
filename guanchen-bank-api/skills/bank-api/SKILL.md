---
name: bank-api
description: "Use the Bank API MCP server to retrieve account data or perform banking workflows. Use when working with Bank API accounts, balances, transactions, beneficiaries, or payments."
argument-hint: "[Bank API task]"
---

# Bank API

1. Establish the requested banking task and the account, transaction, beneficiary, or payment it concerns.
2. Inspect the available Bank API MCP tools and select the least-privileged tool that can complete the task.
3. Complete OAuth authorization in the client when prompted. Never request or expose access tokens, API keys, account numbers, or other sensitive credentials in chat.
4. For any operation that creates, changes, or sends a payment, state the material details and obtain explicit confirmation immediately before making the call.
5. Report the completed operation, relevant non-sensitive identifiers, and any error returned by the service. Do not include unnecessary personal or financial data.