---
name: github
description: "Work with GitHub through the GitHub MCP server. Use when investigating or managing GitHub repositories, issues, pull requests, workflows, branches, releases, or project items."
argument-hint: "[GitHub task or owner/repository]"
---

# GitHub

1. Establish the requested GitHub task, target owner and repository, and whether it is read-only or changes GitHub state.
2. Use the GitHub MCP server's available tools and select the least-privileged tool that can complete the task.
3. For investigations, inspect the current repository state before drawing conclusions or proposing changes.
4. Complete OAuth authorization in the client when prompted. Never request or expose personal access tokens, OAuth tokens, or other credentials in chat.
5. Before deleting content or making a user-visible change that was not explicitly requested, state the target and material details and obtain confirmation immediately before the action.
6. Report the result with relevant GitHub URLs, identifiers, and errors, without including unnecessary sensitive data.