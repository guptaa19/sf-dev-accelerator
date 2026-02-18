# SF Dev Accelerator (Cursor Plugin)

Salesforce plugin for Cursor with broad operational coverage across Salesforce DX MCP and Salesforce CLI.

## Installation

**For Cursor (after Marketplace approval):**

Run this command in chat:

```text
/add-plugin sf-dev-accelerator
```

You can also install from the Cursor Marketplace page when the plugin listing is live.

## How users use this plugin

You do **not** install skills/rules/commands one by one. Installing the plugin adds all bundled components automatically.

- Skills are loaded and applied by the agent when relevant.
- Rules provide persistent guidance for Salesforce-safe defaults.
- Commands provide reusable operation flows (deploy, tests, metadata, data, packaging, etc.).
- Agents provide specialized operating modes (release operator, solution architect).
- MCP config enables Salesforce DX MCP capability routing.

After install, users can work in natural language, for example:

- "List orgs and show my default target org."
- "Validate deployment for this manifest and run local tests."
- "Run Apex tests and summarize failures with probable root causes."
- "Use sf CLI to run `sf org list --all` and explain results."

## What "full capability" means in this plugin

The plugin is designed to handle the complete practical Salesforce development lifecycle:

- Org management and authentication
- Source tracking and metadata lifecycle (retrieve/validate/deploy/quick deploy)
- Apex execution, testing, debugging, and log analysis
- Data operations (query/import/export/upsert/delete)
- User/permission operations
- Package lifecycle (2GP creation/version/install/promotion)
- CI/CD release orchestration
- Generic pass-through execution for any valid `sf` command

## Included Components

- Manifest: `.cursor-plugin/plugin.json`
- MCP configuration: `.mcp.json`
- Skills:
  - `skills/salesforce-full-surface-operations/SKILL.md`
  - `skills/salesforce-architecture/SKILL.md`
  - `skills/apex-design-patterns/SKILL.md`
  - `skills/salesforce-unit-testing/SKILL.md`
  - `skills/lwc-performance-architecture/SKILL.md`
  - `skills/platform-limits-and-scale/SKILL.md`
  - `skills/salesforce-modern-development/SKILL.md`
- Rules:
  - `rules/salesforce-safe-defaults.mdc`
- Agents:
  - `agents/salesforce-release-operator.md`
  - `agents/salesforce-solution-architect.md`
- Commands:
  - `commands/sf-cli-any.md`
  - `commands/mcp-capability-map.md`
  - `commands/org-management.md`
  - `commands/source-tracking.md`
  - `commands/metadata-lifecycle.md`
  - `commands/deploy-validate.md`
  - `commands/retrieve-metadata.md`
  - `commands/run-apex-suite.md`
  - `commands/apex-debug-and-logs.md`
  - `commands/query-org-data.md`
  - `commands/data-operations.md`
  - `commands/user-access-management.md`
  - `commands/package-lifecycle.md`
  - `commands/ci-release-orchestration.md`

## Prerequisites

1. Node.js 18+.
2. Salesforce CLI (`sf`) installed.
3. At least one authenticated org:
   - `sf org login web --alias <alias>`
4. Cursor with plugin support enabled.

## DX MCP Configuration

The plugin includes this baseline:

```json
{
  "mcpServers": {
    "salesforce-dx": {
      "command": "npx",
      "args": [
        "-y",
        "@salesforce/mcp@latest",
        "--orgs",
        "DEFAULT_TARGET_ORG",
        "--allow-non-ga-tools"
      ]
    }
  }
}
```

Tune org aliases and server flags for your environment and governance requirements.

## Usage Examples

Try prompts like:

- "Use Salesforce DX MCP to list my available orgs and show default target org."
- "Validate deployment of my package manifest to UAT with RunLocalTests."
- "Run an Apex test suite and summarize failing tests with likely root causes."
- "Run an sf CLI command: sf org list --all and explain the output."
- "Plan a production release with rollback notes and post-deploy checks."

## Maintainer Notes

- Maintainer/release checklist: `PUBLISH_CHECKLIST.md`
- Plugin manifest: `.cursor-plugin/plugin.json`
- MCP server config: `.mcp.json`

## References

- Cursor Marketplace: https://cursor.com/marketplace
- Cursor plugin docs: https://cursor.com/docs/plugins/building
- Salesforce DX MCP: https://github.com/salesforcecli/mcp
