---
name: sf-cli-any
description: Execute any valid Salesforce CLI command with explicit argument review and result summarization.
---

# SF CLI Any

Use this command when the requested capability is not covered by a curated command or requires exact CLI flags.

## Inputs

- `sfCommand`: full command starting after `sf`, for example `org list --all`.
- `targetOrg`: optional org alias if not already in command args.
- `riskLevel`: `low`, `medium`, or `high`.

## Execution

1. Validate command intent and expected impact.
2. For medium/high risk commands, explicitly confirm execution with user.
3. Execute:
   - `sf <sfCommand>`
4. Return parsed outcome and follow-up recommendations.

## Output

- Exact executed command.
- Exit status and key output lines.
- Suggested next step.
