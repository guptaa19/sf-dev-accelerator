---
name: salesforce-full-surface-operations
description: Operate across the full Salesforce DX MCP and Salesforce CLI capability surface. Use for org administration, metadata workflows, data operations, packaging, CI/CD, debugging, and release execution.
---

# Salesforce Full Surface Operations Skill

## When to use

- User asks to perform any Salesforce operation without limiting scope to a fixed workflow.
- Work spans multiple surfaces: org, metadata, data, users, tests, packaging, and release.
- A task is supported in both MCP and `sf` CLI and requires tool selection.

## Instructions

1. Default tool-selection strategy:
   - Prefer DX MCP tools for structured, high-context interactions.
   - Use `sf` CLI for capabilities not exposed by MCP or when exact CLI flags are requested.
2. Capability promise:
   - Do not constrain execution to only curated commands.
   - If a user asks for a valid Salesforce operation, route it through MCP or `sf` CLI.
3. Safety and execution:
   - Confirm target org, environment, and impact before destructive operations.
   - For deployments, prefer validate/check-only first, then deploy after approval.
4. Operational domains to support:
   - Org auth, discovery, and environment lifecycle.
   - Source tracking, retrieve/deploy/validate metadata.
   - Apex run/test/debug/log analysis.
   - SOQL/data workflows and bulk-safe data handling.
   - User and permission management.
   - Package/version promotion and release tasks.
5. Response quality:
   - Show exact command/tool used.
   - Explain assumptions and required inputs.
   - Provide next actions and rollback notes for high-impact changes.

## Output format

- Requested operation summary.
- Chosen execution path (MCP or `sf` CLI) with rationale.
- Exact command(s) or tool calls.
- Result summary and follow-up actions.
