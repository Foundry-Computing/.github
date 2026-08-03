# Foundry Agent Operating Guide

GitHub Issues are the source of truth for work. Significant work requires an
issue with maintained status, priority, phase, owner, dependencies, and a
completion gate.

Before starting:

1. Inspect repository instructions, existing issues, and Foundry Development.
2. Confirm the canonical source and ownership boundary.
3. Avoid duplicate issues, implementations, and project items.
4. Record blocking dependencies rather than silently changing scope.

During work:

- Keep issue status and material findings current.
- Put architecture decisions in repository documentation or ADRs.
- Require human approval for destructive, costly, public, security-sensitive,
  or privilege-expanding actions.
- Keep commits attributable to the acting identity.
- Attach tests and validation evidence to the issue.
- Produce a completion report for each completed phase.

Preferred lifecycle:

```text
Backlog -> Planned -> Active -> In Review -> Version 1.0 Complete
```

Use `Blocked` when progress cannot continue. Forge may coordinate work but must
not receive unrestricted organization-owner access. GitHub state must remain
clear enough for a smaller model to determine what is active, blocked,
complete, and next without relying on private conversation history.
