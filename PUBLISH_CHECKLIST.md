# Publish Checklist

## Identity and Branding

- [ ] Publish from personal GitHub account (independent maintainer).
- [ ] Ensure no Liberty State references in name, logo, description, or repository.
- [ ] Keep disclaimer in `README.md`:
  - Independent plugin.
  - Not affiliated with Salesforce, Cursor/Anysphere, or Liberty State.

## Metadata Readiness

- [ ] `./.cursor-plugin/plugin.json` name is unique and kebab-case.
- [ ] `author`, `homepage`, and `repository` fields are accurate.
- [ ] Version updated for release (`semver`).
- [ ] License and logo files exist and are referenced correctly.

## Functional Readiness

- [ ] Salesforce CLI installed and authenticated.
- [ ] DX MCP server starts from `.mcp.json`.
- [ ] Curated command workflows execute successfully.
- [ ] Generic `sf-cli-any` path is validated with at least one non-curated command.

## Quality Gates

- [ ] All skills, commands, rules, and agents have valid YAML frontmatter.
- [ ] README documents setup, usage, and troubleshooting.
- [ ] At least one end-to-end release simulation completed:
  - auth -> retrieve -> validate/deploy -> tests -> verification.

## Submission

- [ ] Push plugin code to public GitHub repository.
- [ ] Submit repo URL at `https://cursor.com/marketplace/publish`.
- [ ] Track reviewer feedback and publish revision if needed.
