# Governance

## Decision authority

Foundry Computing is a founder-led organization. Final approval authority for
organization-level decisions remains with @tofonion.

## Repository ownership

Each repository should identify its purpose, maintainers, lifecycle, and review
expectations. Shared organization standards are published from `.github`, but
repositories may impose stronger controls when needed.

## Change approval

- Significant work starts from a GitHub Issue.
- Protected changes go through pull requests.
- At least one human approving review is expected for meaningful changes.
- Security-sensitive, privilege-expanding, destructive, public-facing, or
  release-affecting changes require explicit human approval.

## AI worker boundaries

AI workers may inspect, propose, draft, implement, test, document, and open
pull requests within assigned scope. AI workers must not bypass protections,
approve their own work, merge protected changes without explicit authorization,
or independently change billing, visibility, ownership, authentication,
permissions, secrets, or production environments.

## Emergency changes

Urgent repairs may proceed with abbreviated process only when necessary to
contain harm or restore service, but they still require traceable documentation,
post-change review, and follow-up issue/PR records.

## Archival and deprecation

Repositories or subsystems considered for archival or deprecation should have a
recorded reason, owner review, user impact summary, and recovery considerations
before irreversible action is proposed.

## Exceptions

Exceptions to normal process should be documented with scope, rationale,
approver, and expiration or review condition.
