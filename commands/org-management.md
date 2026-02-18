---
name: org-management
description: Manage Salesforce org authentication, lifecycle, and environment inspection tasks.
---

# Org Management

## Inputs

- `operation`: `list`, `display`, `login`, `logout`, `create-scratch`, `delete-scratch`, `open`.
- `targetOrg`: alias/username where required.
- `durationDays`: scratch org duration for create operation.
- `definitionFile`: path to scratch org definition file when creating scratch org.

## Execution patterns

- List orgs:
  - `sf org list --all`
- Display org:
  - `sf org display --target-org <targetOrg>`
- Login web:
  - `sf org login web --alias <targetOrg>`
- Logout:
  - `sf org logout --target-org <targetOrg> --no-prompt`
- Create scratch org:
  - `sf org create scratch --target-dev-hub <targetOrg> --definition-file <definitionFile> --duration-days <durationDays> --set-default`
- Delete scratch org:
  - `sf org delete scratch --target-org <targetOrg> --no-prompt`
- Open org:
  - `sf org open --target-org <targetOrg>`

## Output

- Org operation result.
- Active default org context.
- Next recommended action.
