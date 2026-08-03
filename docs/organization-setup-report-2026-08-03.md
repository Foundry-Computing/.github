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

Configured least-privilege teams:

| Team | Purpose | Current baseline |
|---|---|---|
| `owners` | Governance and final administration | Human maintainer; maintain access to `.github` |
| `forge` | Future Forge identity and approved automation | Empty; no repository or owner access |
| `engineering` | Active implementation | Human maintainer; write access to `.github` |
| `reviewers` | Review and approval | Human maintainer; triage access to `.github` |

No member or email was fabricated. A future Forge account requires user-controlled identity
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
- Set the organization description, retained read as the default repository
  permission, restricted repository creation to owners, and required web
  commit signoff.
- Created the four teams above and assigned repository-specific permissions.
- Created **Foundry Development** only after both organization and user project
  inventories returned zero projects.
- Configured the project workflow, required fields/options, requested views,
  and all four seed issue items.
- Verified zero organization Actions secrets, variables, and installed Apps by
  name/count. Values were never requested.
- No repository was transferred, no existing visibility changed, no branch was
  renamed, and no ruleset was created. Organization rulesets require a GitHub
  Team plan.

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

## Foundry Development project

Project: https://github.com/orgs/Foundry-Computing/projects/1

Workflow statuses:

`Backlog`, `Planned`, `Active`, `In Review`, `Blocked`, and
`Version 1.0 Complete`.

Required fields are present: Priority, Repository, Product, Epic, Phase, Work
Type, Estimated Effort, Completion Gate, AI Owner, Review Required, and Target
Date. All specified single-select options are configured.

Views are present: Mission Control, Portfolio, Roadmap, Active Work, AI
Workload, Needs Review, Blocked by Repository, Phase 2, Version 1.0 Gates, and
Backlog. API-supported layouts, visible fields, and filters are configured.

Four issue items are linked and populated with status, priority, product,
epic, phase, work type, effort, completion gate, AI owner, and review state.
Target dates remain unset because no approved dates were supplied.

## Manual actions

1. In the project UI, choose grouping/sorting for the saved views and select
   `Target Date` as the Roadmap date field. Project V2 mutations do not expose
   these presentation settings.
2. Enable organization-wide 2FA only after confirming account recovery
   readiness for the sole owner.
3. Add an organization website when a public destination is approved.
4. Upgrade to GitHub Team before adding organization-level rulesets.
5. Create and onboard a dedicated Forge GitHub account only through a separate
   human-controlled identity and credential process.

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
gh auth refresh -h github.com -s admin:org,read:project,project
gh api -X POST orgs/Foundry-Computing/teams
gh api -X PUT orgs/Foundry-Computing/teams/{team}/memberships/{user}
gh api -X PUT orgs/Foundry-Computing/teams/{team}/repos/Foundry-Computing/.github
gh project create --owner Foundry-Computing --title "Foundry Development"
gh project field-create 1 --owner Foundry-Computing
gh project item-add 1 --owner Foundry-Computing
gh project item-edit --project-id {project-id}
gh api graphql  # update Status options and create/update project views
gh api -X PATCH orgs/Foundry-Computing
```

## Rollback guidance

- Profile/community file changes: revert the governance commit and push a new
  revert commit; do not rewrite history.
- Repository metadata: restore the recorded prior values through the repository
  settings API.
- Teams, project fields, views, or items: remove only after explicit human
  approval and an access/dependency review.
- Issues: close with an explanation rather than delete.
