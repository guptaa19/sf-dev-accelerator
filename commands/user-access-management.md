---
name: user-access-management
description: Manage users, permission sets, and access diagnostics in Salesforce orgs.
---

# User Access Management

## Inputs

- `targetOrg`: alias/username.
- `operation`: `list-users`, `assign-permset`, `remove-permset`, `reset-password`, `access-check`.
- `username`: target username when required.
- `permissionSet`: permission set name when required.

## Execution patterns

- List users:
  - `sf data query --query "SELECT Id, Username, IsActive, Profile.Name FROM User LIMIT 200" --target-org <targetOrg>`
- Assign permset:
  - `sf org assign permset --name <permissionSet> --target-org <targetOrg> --on-behalf-of <username>`
- Remove permset:
  - Execute permission set removal strategy approved by user.
- Reset password:
  - `sf org generate password --target-org <targetOrg> --on-behalf-of <username>`
- Access check:
  - Run focused queries and summarize profile/permset posture.

## Output

- Access operation summary.
- Security impact notes.
- Follow-up verification actions.
