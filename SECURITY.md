# Security Policy

## Reporting vulnerabilities

Do not disclose credentials, private infrastructure details, personal data, or
unpatched vulnerabilities in public issues or discussions.

If private vulnerability reporting is enabled for the affected repository, use
that channel. Otherwise contact an organization owner through an approved
private path. Never send secrets as evidence.

Reports should identify the affected repository and version, describe impact,
provide minimized reproduction details, and note any known containment steps.

## Security-sensitive work

The following require explicit security-aware human review:

- authentication and authorization changes
- secret handling and token exposure risk
- destructive operations and recovery procedures
- permission, billing, visibility, or ownership changes
- production deployment paths and network exposure

## Baseline expectations

- Use least privilege for humans, automation, and AI accounts.
- Do not weaken branch protections, review requirements, or Actions restrictions.
- Document tests performed and any incomplete validation.
- Stop and request approval when a change affects billing, authentication,
  ownership, repository visibility, secret access, or other irreversible risk.
