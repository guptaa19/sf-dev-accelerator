# SF Dev Accelerator (Cursor Plugin)

Salesforce plugin for Cursor with broad operational coverage across Salesforce DX MCP and Salesforce CLI.

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

## Local Validation Checklist

- Plugin name is unique, lowercase, and kebab-case.
- Paths in manifest are relative and valid.
- All `SKILL.md`, commands, agents, and rules contain valid frontmatter.
- `.mcp.json` parses and MCP server starts in Cursor.
- At least one full flow succeeds:
  - org auth -> retrieve -> validate/deploy -> tests -> post-check.

## Publish Workflow

1. Push this plugin folder to a public Git repository.
2. Confirm `author`, `homepage`, and `repository` values in `.cursor-plugin/plugin.json`.
3. Submit repository via `https://cursor.com/marketplace/publish`.
4. Address review feedback and republish.

## Best-Practice Sources

- Cursor:
  - https://cursor.com/marketplace
  - https://cursor.com/docs/plugins/building
- Salesforce:
  - https://architect.salesforce.com/well-architected/overview
  - https://architect.salesforce.com/docs/architect/well-architected-tools/guide/patterns
  - https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_gov_limits.htm
  - https://developer.salesforce.com/docs/platform/lwc/guide/perf-intro.html
  - https://trailhead.salesforce.com/content/learn/modules/apex_testing/apex_testing_intro
  - https://developer.salesforce.com/blogs/2025/01/spring25-developers
  - https://developer.salesforce.com/blogs/2026/01/developers-guide-to-the-spring-26-release
  - https://github.com/salesforcecli/mcp
