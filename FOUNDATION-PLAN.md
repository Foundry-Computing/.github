# FOUNDATION-PLAN

Date: 2026-08-04
Organization: `Foundry-Computing`
Scope repository: `/home/runner/work/.github/.github`

## Target structure

### Organization model

- one GitHub organization: `Foundry-Computing`
- `@tofonion` remains final approval authority
- human approval remains required for ownership, security-sensitive work, releases, and access expansion
- AI accounts operate with least privilege and repository-scoped access only

### Proposed team model

Create or align to the following teams only where equivalent teams do not already exist:

- `owners`
- `core-platform`
- `desktop`
- `infrastructure`
- `automation`
- `knowledge-base`
- `banking`
- `documentation`
- `security`
- `ai-workers`

Team design principles:

- `owners` is documentation and coordination only; it does not replace GitHub Owner role
- repository access should be granted per-team and per-repository, not broadly by default
- AI accounts default to read, triage, or narrowly scoped write access
- AI accounts must not administer repositories, manage secrets, bypass branch protections, or self-approve

### Standard repository model

Recommended default for active repositories:

- default branch `main`
- changes through pull requests
- at least one required approving review
- dismiss stale approvals on new commits
- require conversation resolution before merge
- require status checks when a repository has tests/build validation
- prevent force pushes and branch deletion on protected branches
- no direct pushes by AI workers to protected branches
- prefer squash merge
- auto-delete merged feature branches where appropriate
- maintain description, topics, README, documented license decision, CONTRIBUTING, SECURITY, CODE_OF_CONDUCT, SUPPORT, issue forms, PR template, CODEOWNERS, and Dependabot config where applicable

### Repository classification model

Document these classifications for future adoption:

- core platform
- application
- integration
- infrastructure
- knowledge archive
- user interface
- automation
- library
- experimental
- archived

Each active repository should eventually document purpose, owner, maintainers, lifecycle, supported environments, dependencies, build/test instructions, release process, backup/recovery considerations, security sensitivity, and AI access level.

## Staged rollout

### Stage 1 — discovery and documentation

- record current state, risks, and gaps
- separate live-verified state from prior documented state and permission-limited areas
- preserve all existing repository content

### Stage 2 — foundation repository update

- update `Foundry-Computing/.github` on a feature branch
- add missing governance documents
- expand organization profile
- replace minimal issue forms with structured reusable forms
- expand PR template
- add CODEOWNERS
- add changelog, rollback, and repository adoption checklist

### Stage 3 — review and approval

- open pull request for owner review
- capture validation evidence
- identify org-level follow-up items that require explicit approval or broader permissions

### Stage 4 — post-merge adoption

Recommended rollout order after review:

1. `.github` repository and org profile
2. active core repositories with human maintainers available
3. automation/infrastructure repositories with highest governance sensitivity
4. experimental and lower-risk repositories
5. archival review and lifecycle tagging for dormant repositories

## Approval points

Explicit owner approval should be obtained before:

- any organization membership or role changes
- any team creation or team permission expansion outside this repo if not already approved
- any default-branch protection or org ruleset changes
- Actions policy enforcement that could block existing workflows
- 2FA or authentication-policy requirements
- security feature enablement that may affect billing or access
- repository creation/deletion/transfer/visibility changes

## Rollback considerations

Repository-content changes in `.github` are reversible with follow-up commits that restore previous files.

Potentially disruptive follow-up actions outside this repository should each have:

- recorded previous state
- explicit owner approval
- repository-by-repository rollout
- a rollback step that restores prior settings if no destructive side effect has occurred

## Proposed label taxonomy

Standardize toward these groups without creating near-duplicates:

- Type: `type: bug`, `type: feature`, `type: task`, `type: documentation`, `type: security`, `type: maintenance`, `type: research`
- Priority: `priority: critical`, `priority: high`, `priority: medium`, `priority: low`, `priority: someday`
- Status: `status: needs-triage`, `status: planned`, `status: active`, `status: blocked`, `status: needs-review`, `status: ready`, `status: completed`
- Effort: `effort: xs`, `effort: s`, `effort: m`, `effort: l`, `effort: xl`
- Work ownership: `owner: human`, `owner: copilot`, `owner: codex`, `owner: forge`, `owner: local-ai`
- Risk: `risk: low`, `risk: moderate`, `risk: high`, `risk: destructive`, `risk: security-sensitive`
- Product areas: only labels that map to real repositories or active products

## Actions policy proposal

- use least-privilege default workflow token permissions
- pin third-party actions to immutable SHAs where practical
- do not expose secrets to workflows triggered from untrusted forks
- require human approvals for sensitive environments and deployments
- separate validation, build, release, and deployment workflows
- centralize reusable workflows in a controlled repository when introduced
- require review for workflow changes affecting protected release or deployment paths

## Security baseline proposal

- keep least-privilege org membership and review outside collaborators regularly
- require careful owner-reviewed path before enabling org-wide 2FA/passkey enforcement
- document account recovery expectations before auth tightening
- prefer restrictive repository creation and transfer permissions
- enable secret scanning, Dependabot alerts, security updates, push protection, private vulnerability reporting, and code scanning only after confirming plan support and repository applicability
- do not enable settings that can lock out the sole owner without a tested recovery path
