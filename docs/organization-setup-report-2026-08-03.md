# Foundry Computing Organization Setup Report

Date: 2026-08-03
Organization: `Foundry-Computing`

## Initial inventory

- Display name: Foundry Computing
- Description and website: not configured
- Repositories: none
- Members: one human organization administrator
- Teams and outside collaborators: none visible
- Default repository permission: read
- Member repository creation: public and private enabled
- Two-factor requirement: not enabled
- Web commit signoff requirement: not enabled
- Profile repository: absent
- Organization rulesets, Actions secrets/variables, audit log, and installed
  application details: unavailable with the current token permissions
- GitHub Projects: unavailable with the current token's project scopes

Secret and variable values were never requested or displayed.

## Governance model

Planned least-privilege teams:

| Team | Purpose | Intended baseline |
|---|---|---|
| `owners` | Governance and final administration | Human owners only |
| `forge` | Future Forge identity and approved automation | Empty until separately onboarded; no owner access |
| `engineering` | Active implementation | Repository write only where needed |
| `reviewers` | Review and approval | Read/triage by default; repository-specific elevation |

Team creation requires an authenticated token with `admin:org`. No member or
email is fabricated. A future Forge account requires user-controlled identity
verification, protected credentials, attributable commits, and repository-
specific least privilege.

## Resources created or modified

- Created the public `.github` organization profile and governance repository.
- Set its description and topics: `foundry-computing`, `forge`, `governance`,
  and `community-health`.
- Enabled Issues and repository Projects, disabled Wiki and Discussions, and
  enabled deletion of merged branches.
- Added the public profile, reusable community health files, issue and pull
  request templates, this agent guide, and this setup report.
- Added machine-readable labels for status, priority, product, phase, work
  type, AI owner, and review requirement.
- Created four non-duplicative seed issues:
  - [Forge Core Phase 2A](https://github.com/Foundry-Computing/.github/issues/1)
  - [Forge Core Phase 2B](https://github.com/Foundry-Computing/.github/issues/2)
  - [forge-vscode Phase 0/1A](https://github.com/Foundry-Computing/.github/issues/3)
  - [GitHub Organization Foundation](https://github.com/Foundry-Computing/.github/issues/4)
- No organization visibility, member, team, repository-transfer, branch,
  ruleset, secret, variable, or project-v2 resource was changed.

## Branch and repository policy

- Use `main` for new repositories.
- Do not automatically rename existing `master` branches.
- Plan each rename around clones, CI, documentation, dependencies, and open PRs.
- Add default-branch protection only when real checks and a non-locking review
  path exist.
- Preserve repository visibility and require approval before transfers.

## Repository migration matrix

| Repository | Current owner | Proposed organization | Visibility | Default branch | Active dependencies | Transfer risk | Recommended action | Approval required |
|---|---|---|---|---|---|---|---|---|
| `forge-core` | Local canonical source | Foundry Computing | Not published | `master` | Gateway, future clients | High: active unstaged Phase 2A | Review and commit locally, then plan first publication | Yes |
| `foundry-ai-gateway` | Local canonical source | Foundry Computing | Not published | Feature branch observed | Ollama, Forge Core | High: existing worktree changes | Complete repository review before publication | Yes |
| `foundry-powershell-module` | Local canonical source | Foundry Computing | Not published | Existing release branch | Core migration planned | High: deployed module and active changes | Publish only after source/install review | Yes |
| `forge-vscode` | Not created | Foundry Computing | Undecided | `main` proposed | Forge Client API | Medium: new repository | Create after Phase 2A approval | Yes |
| `.github` | Created by this setup | Foundry Computing | Public | `main` | Organization governance | Low | Maintain as organization profile/governance source | No further transfer |

No repository was transferred, renamed, or made visible by migration.

## Foundry Development project specification

The token cannot inspect Projects, so no project was created and no duplicate
risk was taken. Required statuses, fields, values, and views remain those in
the approved organization setup task. After project scopes are granted, first
list projects and update **Foundry Development** if present.

## Manual actions

1. Grant the CLI the required scopes using
   `gh auth refresh -h github.com -s admin:org -s read:project -s project`.
2. Re-inventory teams, applications, rulesets, secrets/variables by name, and
   Foundry Development before making those changes.
3. Create least-privilege teams and leave `forge` empty until a dedicated
   account is approved.
4. Configure Foundry Development fields, options, views, and seed issue items.
5. Review whether to restrict member repository creation and require 2FA; do
   not enable either until the sole owner confirms account recovery readiness.
6. Add organization description and website after the public URL is approved.

## Commands used

Commands are shown without credentials or workstation-specific paths:

```text
gh auth status
gh api user
gh api user/orgs
gh api orgs/Foundry-Computing
gh repo list Foundry-Computing
gh api orgs/Foundry-Computing/teams
gh api orgs/Foundry-Computing/members
gh api orgs/Foundry-Computing/outside_collaborators
gh project list --owner Foundry-Computing --format json
gh repo create Foundry-Computing/.github --public
gh api -X PATCH repos/Foundry-Computing/.github
gh api -X PUT repos/Foundry-Computing/.github/topics
gh label create --repo Foundry-Computing/.github
gh issue list --repo Foundry-Computing/.github --state all
gh issue create --repo Foundry-Computing/.github
```

## Rollback guidance

- Profile/community file changes: revert the governance commit and push a new
  revert commit; do not rewrite history.
- Repository metadata: restore the recorded prior values through the repository
  settings API.
- Teams or project fields created later: remove only after explicit human
  approval and an access/dependency review.
- Issues: close with an explanation rather than delete.
