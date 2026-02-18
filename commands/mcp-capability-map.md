---
name: mcp-capability-map
description: Discover and route tasks to the appropriate Salesforce DX MCP tools before falling back to sf CLI.
---

# MCP Capability Map

Use this command to choose the best execution path for a user request.

## Inputs

- `taskDescription`: plain-language task statement.
- `targetOrg`: alias/username.

## Execution

1. Map request to capability domain:
   - orgs, metadata, data, users, logic, testing, deployment, packaging, or debugging.
2. Prefer DX MCP tools when available.
3. If MCP tool is unavailable, route to equivalent `sf` CLI command.
4. Return a concise execution plan and run it after user confirmation for medium/high risk operations.

## Output

- Capability-domain mapping.
- Selected tool path (MCP vs CLI).
- Exact command/tool call sequence.
