# FOUNDATION-ASSESSMENT

Date: 2026-08-04
Organization: `Foundry-Computing`
Assessment repository: `/home/runner/work/.github/.github`
Assessment branch: `copilot/organize-org-tofonion-foundry-computing`

## Scope and method

This assessment combines:

- repository state visible in `/home/runner/work/.github/.github`
- GitHub repository metadata visible for `Foundry-Computing/.github`
- visible collaborators, branches, issues, labels, and discussion state for `Foundry-Computing/.github`
- previously recorded organization setup data in `/home/runner/work/.github/.github/docs/organization-setup-report-2026-08-03.md`

No discovery-stage changes were applied before this assessment was written.

## Executive inventory

### Currently configured

| Area | Current state | Evidence |
|---|---|---|
| Organization profile repository | `.github` repository exists and is public | GitHub repository search result; local repo clone |
| Repository description/topics | Description and topics are configured | GitHub repository metadata |
| Default branch | `.github` default branch is `main` | GitHub repository metadata |
| Branching | `main` and feature branch `copilot/organize-org-tofonion-foundry-computing` exist | GitHub branch list |
| Visible admin on `.github` | `@tofonion` has admin access to `.github` | repository collaborator listing |
| Baseline governance files | `README.md`, `profile/README.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `SUPPORT.md`, and PR template exist | local files |
| Issue templates | `bug.yml`, `work.yml`, and `config.yml` exist | local files |
| Existing governance assessment | prior setup report exists | `/docs/organization-setup-report-2026-08-03.md` |
| Issues as source of truth | issue #4 already tracks organization foundation work | GitHub issue search |
| Labels | baseline status/priority/product/phase/work-type/AI/review labels exist, in addition to default GitHub labels | label listing |
| Discussions in `.github` repo | none present | discussions listing |
| Reusable workflows | none present in this repository | local tree |
| Dependabot config in `.github` repo | none present | local tree |
| CODEOWNERS in `.github` repo | none present | local tree |

### Partially configured

| Area | Current state | Gap |
|---|---|---|
| Organization profile | mission statement exists, but contributor entry points, workflow, repository organization model, approval model, and preservation values are only partially documented | needs fuller profile README |
| Contribution guidance | basic contribution guidance exists | needs organization-wide workflow, issue linkage, validation, and AI disclosure expectations |
| Security guidance | basic public-reporting guidance exists | needs fuller baseline, escalation, repository settings expectations, and AI/security boundaries |
| PR template | basic sections exist | missing required fields from requested standard |
| Issue forms | bug and planned work forms exist | missing feature request, project task, and documentation request forms; existing forms need expanded structure |
| Governance docs | setup report and AGENTS.md exist | missing dedicated governance, AI policy, release policy, project management, repository standards, rollback, and changelog documents |
| Label taxonomy | a useful seed taxonomy exists | naming does not yet match proposed standard and several label groups are missing |
| Foundry Development project documentation | prior report says project exists with fields and views | current token cannot inspect project directly in this session, so the state is only partially verified |

### Missing

| Area | Missing item |
|---|---|
| Discovery deliverables | `FOUNDATION-PLAN.md`, `FOUNDATION-CHANGELOG.md`, `FOUNDATION-ROLLBACK.md`, `REPOSITORY-ADOPTION-CHECKLIST.md` |
| Community health files | `GOVERNANCE.md`, `AI-CONTRIBUTION-POLICY.md`, `REPOSITORY-STANDARDS.md`, `PROJECT-MANAGEMENT.md`, `RELEASE-POLICY.md` |
| Issue forms | `feature_request.yml`, `project_task.yml`, `documentation.yml` |
| CODEOWNERS | no organization-wide CODEOWNERS file in `.github` repo |
| Pull request standard | requested reviewer/completion checklist and AI disclosure sections are not present |
| Repository standards guidance | no reusable adoption checklist or rollout order document |
| Dependabot policy/config | no documented org-level approach in repo and no config file in `.github` repo |
| Foundation change log | no per-change audit log for this phase |
| Foundation rollback guide | no dedicated rollback instructions for the requested deliverables |

### Blocked by permissions or visibility

| Area | Limitation | Effect |
|---|---|---|
| Organization repositories inventory | available API visibility in this session only reveals `.github` | full org inventory cannot be independently verified from current access |
| Organization members and roles | only `.github` collaborator data is directly visible in this session | cannot fully verify all org members, outside collaborators, or org roles |
| Existing teams | no organization team read tool is available in this environment | team inventory relies on prior report and cannot be revalidated directly |
| Organization Projects | direct project inspection tools are not available in this environment | prior report can be summarized, but fields/views/workflows cannot be re-read live |
| Organization-level Actions/security settings | no org settings read tool is available here | assessment must distinguish documented prior state from live-verified state |
| Rulesets and branch protection across all repos | no repository-wide settings enumeration tool is available for the whole org | can only assess `.github` branch protection from visible branch metadata |
| Secret scanning, code scanning, and Dependabot across all repos | security feature state is not directly enumerable with current tools for the entire org | only propose/document baseline |

### Requires owner approval before applying

| Area | Approval reason |
|---|---|
| Granting organization Owner role | explicitly prohibited without approval; request also forbids granting owner access |
| Authentication policy changes such as mandatory 2FA or passkeys | may affect account access and recovery |
| Repository visibility changes | explicitly approval-gated |
| Repo transfer, deletion, archival, rename, or default-branch renames | irreversible or disruptive |
| Team creation and org-wide permission changes | affect access control beyond repository documentation |
| Branch protections/rulesets applied org-wide | can affect contributor workflows and may lock out work if misconfigured |
| Actions restrictions and fork approval policies | can block builds or contributor workflows |
| Secret scanning/push protection changes where plan/billing may apply | may have plan or security implications |

### May require a paid GitHub plan

| Area | Why it may require paid plan |
|---|---|
| Organization rulesets | prior report states org rulesets require GitHub Team for this org |
| Some advanced security features | secret scanning, push protection, code scanning, and private vulnerability reporting may vary by repository visibility and plan |
| Advanced project/portfolio automation | some project capabilities may depend on plan scope or token permissions |

## Repository-level findings for `Foundry-Computing/.github`

| Topic | Observation |
|---|---|
| Visibility | Public |
| Default branch | `main` |
| Protected default branch | not indicated by available branch metadata |
| Feature branch workflow | current working branch is `copilot/organize-org-tofonion-foundry-computing` |
| Open pull requests | none currently open |
| Default health files | present but minimal |
| Issue templates | present but incomplete versus requested foundation |
| PR template | present but incomplete versus requested foundation |
| Discussions | no discussions/categories present in `.github` repo |
| Labels | existing taxonomy differs from proposed new standard |
| CODEOWNERS | absent |
| Dependabot config | absent |
| Reusable workflows | absent |

## Risks and control gaps

1. `.github` currently appears to have no protected default branch based on visible branch metadata.
2. Organization governance guidance exists, but the requested AI, release, project, repository, and approval policies are not yet codified in reusable documents.
3. Existing issue templates and labels are inconsistent with the more structured operating model requested for human-and-AI coordination.
4. The prior setup report indicates useful org/project configuration already exists; careless replacement could overwrite valid work, so updates must merge with existing content rather than replace it wholesale.
5. Several requested discovery items cannot be live-verified from the current permission/tool surface and must remain explicitly marked as blocked or previously documented.

## Recommended priorities

1. Complete written foundation assessment, plan, rollback, changelog, and adoption checklist in this repository.
2. Expand the `.github` repository’s reusable governance and community-health files without overwriting existing useful content.
3. Add structured issue forms, a fuller pull request template, and CODEOWNERS for default review routing.
4. Document a conservative organization/team/repository standard that preserves human approval and least privilege for AI accounts.
5. Present, but do not apply, owner-approval items for org membership policy, branch/ruleset enforcement, Actions restrictions, and security feature rollout.

## Safe implementation boundary for this phase

Safe repository changes in this phase:

- add or update documentation files in `Foundry-Computing/.github`
- add or update issue forms and pull request templates in `Foundry-Computing/.github`
- add organization profile and standards documentation
- add a CODEOWNERS file scoped to this repository if it does not weaken protection

Not safe to apply in this phase without explicit owner approval or broader permissions:

- granting owner/admin authority
- changing org membership policy
- changing repository visibility
- deleting or transferring anything
- creating secrets, apps, tokens, or integrations
- changing org-wide authentication, billing, or paid features
- weakening protections or bypassing review requirements
