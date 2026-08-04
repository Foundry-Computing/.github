# Foundry roadmap issue import artifacts
Date: 2026-08-04
Source draft: `/home/runner/work/.github/.github/docs/foundry-roadmap-issue-backlog-2026-08-04.md`
Purpose: repository-safe import artifacts for converting the approved roadmap draft into GitHub issues and Foundry Development project items.

## Usage
1. Create one GitHub issue per artifact below using the matching repository issue template when possible.
2. After issue creation, set Foundry Development fields for Status, Priority, Repository, Product, Epic, Phase, Work Type, Estimated Effort, Completion Gate, AI Owner, Review Required, and Target Date as applicable.
3. Translate requested labels to the nearest available taxonomy if the exact label does not yet exist.
4. Keep these artifacts planning-only; do not expand them into implementation scope during import.

## Import sequence
1. A2
2. A1
3. A3
4. A4
5. A5
6. A6
7. A7
8. A8
9. A9
10. R1
11. R2
12. R3
13. R4
14. R5
15. R6
16. G1
17. G2
18. G3
19. G4

## Project field mapping
- Workflow status: `Backlog`
- AI owner: `none`
- Review required: `yes`
- Estimated effort mapping: `S -> Low`, `M -> Medium`, `L -> High`
- Repository/project fields should preserve the future repository destination text from the source draft when applicable.

## Issue artifacts

### A2 — Epic — Forge Arcade Phase 1-7 planning backlog
- Template: feature_request.yml
- Native issue type intent: Epic
- Suggested labels: `epic`, `forge`, `future`, `backlog`, `architecture`
- Priority: High
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `none`
- Phase field: `1-7`
- Work Type field: `Epic`
- Estimated Effort field: `High`
- Completion Gate field: Child planning issues exist for each approved roadmap phase; dependency order reflects the roadmap; intended destination repository is recorded.

**Body**
Track the approved long-term Forge Arcade and Forge Game Workshop roadmap as a single planning epic with child issues for each major phase.

**Motivation**
The approved roadmap should be represented as executable backlog structure without prematurely expanding into implementation tasks.

**Scope**
- Track approved phases for library/launcher, celebrations, workshop, playtesting, idle creative mode, milestone archive, and hardening.
- Preserve architectural boundaries between Forge, Forge Arcade, Forge Game Workshop, and TIC-80.
- Maintain child issue ordering and dependency structure.

**Out of Scope**
- Production implementation.
- Runtime execution, asset generation, or cartridge publishing.

**Acceptance Criteria**
- Child planning issues exist for each approved roadmap phase.
- Dependency order reflects the roadmap.
- Intended destination repository is recorded.

**Dependencies and Notes**
- Related docs: `/home/runner/work/.github/.github/docs/third-party/tic80-foundry-notes/FORGE-ARCADE-ROADMAP.md`

### A1 — Forge Arcade Phase 0 — TIC-80 research, metadata pinning, and runtime boundary review
- Template: feature_request.yml
- Native issue type intent: Research
- Suggested labels: `documentation`, `research`, `forge`, `future`, `backlog`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2` after issue creation
- Phase field: `0`
- Work Type field: `Research`
- Estimated Effort field: `Medium`
- Completion Gate field: Upstream TIC-80 metadata is verified and recorded; candidate version pin or release options are documented; runtime/security boundary findings are documented; findings link back to roadmap and notes.

**Body**
Establish the approved Phase 0 research baseline for TIC-80 as a contained runtime dependency inside Forge Arcade and Forge Game Workshop.

**Motivation**
Forge Arcade planning requires a verified third-party runtime baseline before any integration or implementation work is scheduled.

**Scope**
- Preserve and document the approved upstream TIC-80 dependency strategy.
- Record current upstream metadata, version pinning candidates, and licensing.
- Review supported platforms, editor workflows, demos, and build prerequisites.
- Review runtime and security boundaries for later phases.
- Record findings in Foundry planning artifacts.

**Out of Scope**
- Forge Arcade implementation.
- Cartridge generation.
- Runtime integration into Forge.
- Launching untrusted cartridges in production workflows.

**Acceptance Criteria**
- Upstream TIC-80 metadata is verified and recorded.
- Candidate version pin or release options are documented.
- Runtime/security boundary findings are documented.
- Findings link back to roadmap and notes.

**Dependencies and Notes**
- Parent issue: A2
- Repositories: `.github` (temporary planning home), future `Foundry-Forge-Arcade`
- Notes: `/home/runner/work/.github/.github/docs/third-party/tic80-foundry-notes/FORGE-ARCADE-ROADMAP.md`

### A3 — Forge Arcade Phase 1 — Arcade library, launcher, and cartridge approval planning
- Template: feature_request.yml
- Native issue type intent: Feature
- Suggested labels: `enhancement`, `forge`, `ui`, `future`, `backlog`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2`
- Phase field: `1`
- Work Type field: `Feature`
- Estimated Effort field: `High`
- Completion Gate field: Planning issue defines approval workflow, metadata expectations, and launcher boundaries; architecture notes distinguish trusted metadata handling from runtime execution.

**Scope**
- Catalog approved `.tic` cartridges.
- Store metadata and hashes.
- Plan controlled runtime launching.
- Plan score and play-history tracking.
- Plan manual import and approval workflow.

**Acceptance Criteria**
- Planning issue defines approval workflow, metadata expectations, and launcher boundaries.
- Architecture notes distinguish trusted metadata handling from runtime execution.

**Dependencies and Notes**
- Parent issue: A2
- Blocking issue: A1
- Related issues: A4-A9

### A4 — Forge Arcade Phase 2 — Achievement celebrations planning
- Template: feature_request.yml
- Native issue type intent: Feature
- Suggested labels: `enhancement`, `forge`, `persona`, `future`, `backlog`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2`
- Phase field: `2`
- Work Type field: `Feature`
- Estimated Effort field: `Medium`
- Completion Gate field: Tiered celebration model is represented in backlog; external sensitive systems remain indirect event sources only.

**Scope**
- Define normalized achievement events.
- Define reusable celebration templates and celebration tiers.
- Plan approved event-source integration boundaries.
- Plan mute, postpone, replay, and accessibility controls.

**Acceptance Criteria**
- Tiered celebration model is represented in backlog.
- External sensitive systems remain indirect event sources only.

**Dependencies and Notes**
- Parent issue: A2
- Blocking issue: A3

### A5 — Forge Game Workshop Phase 3 — Cartridge creation workflow planning
- Template: feature_request.yml
- Native issue type intent: Feature
- Suggested labels: `enhancement`, `forge`, `future`, `backlog`, `architecture`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2`
- Phase field: `3`
- Work Type field: `Feature`
- Estimated Effort field: `High`
- Completion Gate field: Workshop planning captures generation, validation, and approval boundaries; issue explicitly treats generated cartridges as untrusted artifacts.

**Scope**
- Plan natural-language game planning.
- Plan Lua-first cartridge project generation.
- Plan asset generation, static validation, manifests, and approval submission.

**Acceptance Criteria**
- Workshop planning captures generation, validation, and approval boundaries.
- Issue explicitly treats generated cartridges as untrusted artifacts.

**Dependencies and Notes**
- Parent issue: A2
- Blocking issue: A4

### A6 — Forge Game Workshop Phase 4 — Automated playtesting planning
- Template: feature_request.yml
- Native issue type intent: Research
- Suggested labels: `research`, `forge`, `future`, `backlog`, `architecture`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2`
- Phase field: `4`
- Work Type field: `Research`
- Estimated Effort field: `Medium`
- Completion Gate field: Telemetry assumptions are documented as future research; isolation and hostile-code assumptions remain explicit.

**Scope**
- Plan isolated TIC-80 execution.
- Plan simulated controller input and screenshot capture.
- Plan telemetry conventions, crash/hang detection, and playtest reports.

**Acceptance Criteria**
- Telemetry assumptions are documented as future research.
- Isolation and hostile-code assumptions remain explicit.

**Dependencies and Notes**
- Parent issue: A2
- Blocking issue: A5

### A7 — Forge Arcade Phase 5 — Idle Creative Mode policy planning
- Template: feature_request.yml
- Native issue type intent: Security
- Suggested labels: `security`, `forge`, `future`, `backlog`, `documentation`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2`
- Phase field: `5`
- Work Type field: `Security`
- Estimated Effort field: `Medium`
- Completion Gate field: Budget, privacy, and approval constraints are explicit; no implementation work is scheduled beyond planning.

**Scope**
- Plan resource budgets, scheduling controls, private draft handling, and review queue behavior for idle cartridge creation.
- Preserve the approved non-interruption and privacy constraints.

**Acceptance Criteria**
- Budget, privacy, and approval constraints are explicit.
- No implementation work is scheduled beyond planning.

**Dependencies and Notes**
- Parent issue: A2
- Blocking issue: A6

### A8 — Forge Arcade Phase 6 — Milestone archive and replay planning
- Template: feature_request.yml
- Native issue type intent: Feature
- Suggested labels: `enhancement`, `forge`, `future`, `backlog`
- Priority: Low
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2`
- Phase field: `6`
- Work Type field: `Feature`
- Estimated Effort field: `Medium`
- Completion Gate field: Archive, migration, and replay expectations are documented in backlog form.

**Scope**
- Plan permanent playable achievement scrapbook behavior.
- Plan versioned cartridge preservation, migration, backup, and replay.

**Acceptance Criteria**
- Archive, migration, and replay expectations are documented in backlog form.

**Dependencies and Notes**
- Parent issue: A2
- Blocking issue: A7

### A9 — Forge Arcade Phase 7 — Production hardening and open-source readiness planning
- Template: feature_request.yml
- Native issue type intent: Security
- Suggested labels: `security`, `architecture`, `future`, `backlog`, `forge`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Product field: `Forge Arcade`
- Epic field: `A2`
- Phase field: `7`
- Work Type field: `Security`
- Estimated Effort field: `High`
- Completion Gate field: Hardening and release-readiness gates are explicit and separate from feature implementation.

**Scope**
- Threat modeling
- Security review
- Runtime hardening
- Accessibility review
- Licensing review
- Reproducible builds
- Backup and restore
- Plugin or SDK boundary planning
- Public documentation and open-source release planning

**Acceptance Criteria**
- Hardening and release-readiness gates are explicit and separate from feature implementation.

**Dependencies and Notes**
- Parent issue: A2
- Blocking issue: A8

### R1 — Epic — Forge Remote Terminal roadmap planning backlog
- Template: feature_request.yml
- Native issue type intent: Epic
- Suggested labels: `epic`, `future`, `backlog`, `mobile`, `infrastructure`, `architecture`
- Priority: High
- Repository field: `.github` now; intended future repository: `Forge Remote Terminal`
- Product field: `Forge Remote Terminal`
- Epic field: `none`
- Phase field: `Follow-up`
- Work Type field: `Epic`
- Estimated Effort field: `High`
- Completion Gate field: Child planning issues exist for each approved phase; Mosh remains an upstream-tracked dependency, not the product boundary.

**Body**
Represent the approved Forge Remote Terminal roadmap as a planning epic with phase-ordered child issues.

**Scope**
- Preserve the approved planning scope from the source draft.

**Acceptance Criteria**
- Child planning issues exist for each approved phase.
- Mosh remains an upstream-tracked dependency, not the product boundary.

**Dependencies and Notes**
- Related doc: `/home/runner/work/.github/.github/docs/third-party/mosh-foundry-notes/FORGE-REMOTE-TERMINAL-ROADMAP.md`

### R2 — Forge Remote Terminal Phase 0 — Mosh research and transport boundary review
- Template: feature_request.yml
- Native issue type intent: Research
- Suggested labels: `research`, `mobile`, `future`, `backlog`, `documentation`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Forge Remote Terminal`
- Product field: `Forge Remote Terminal`
- Epic field: `R1`
- Phase field: `0`
- Work Type field: `Research`
- Estimated Effort field: `Medium`
- Completion Gate field: Upstream transport research is documented; security and firewall concerns are explicit.

**Scope**
- Preserve upstream Mosh.
- Record version, branch, license, and prerequisites.
- Review supported operating systems, firewall needs, and security history.
- Preserve the transport abstraction boundary.

**Acceptance Criteria**
- Upstream transport research is documented.
- Security and firewall concerns are explicit.

**Dependencies and Notes**
- Parent issue: R1

### R3 — Forge Remote Terminal Phase 1 — Transport abstraction planning
- Template: feature_request.yml
- Native issue type intent: Infrastructure
- Suggested labels: `infrastructure`, `mobile`, `future`, `backlog`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Forge Remote Terminal`
- Product field: `Forge Remote Terminal`
- Epic field: `R1`
- Phase field: `1`
- Work Type field: `Infrastructure`
- Estimated Effort field: `Medium`
- Completion Gate field: Transport abstraction and fallback requirements are explicit.

**Scope**
- Define transport interface.
- Plan SSH baseline and optional Mosh adapter.
- Plan fallback behavior and user-visible transport handling.

**Acceptance Criteria**
- Transport abstraction and fallback requirements are explicit.

**Dependencies and Notes**
- Parent issue: R1
- Blocking issue: R2

### R4 — Forge Remote Terminal Phase 2 — Device and session management planning
- Template: feature_request.yml
- Native issue type intent: Feature
- Suggested labels: `enhancement`, `mobile`, `future`, `backlog`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Forge Remote Terminal`
- Product field: `Forge Remote Terminal`
- Epic field: `R1`
- Phase field: `2`
- Work Type field: `Feature`
- Estimated Effort field: `Medium`
- Completion Gate field: Session management and audit requirements are captured.

**Scope**
- Plan device enrollment.
- Plan session discovery, reconnect, credential handling, and audit metadata.
- Plan TC57-focused interface work.

**Acceptance Criteria**
- Session management and audit requirements are captured.

**Dependencies and Notes**
- Parent issue: R1
- Blocking issue: R3

### R5 — Forge Remote Terminal Phase 3 — Forge session integration planning
- Template: feature_request.yml
- Native issue type intent: Feature
- Suggested labels: `enhancement`, `forge`, `mobile`, `future`, `backlog`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Forge Remote Terminal`
- Product field: `Forge Remote Terminal`
- Epic field: `R1`
- Phase field: `3`
- Work Type field: `Feature`
- Estimated Effort field: `Medium`
- Completion Gate field: Structured-session boundary is explicit; approval and audit requirements are preserved.

**Scope**
- Plan Forge Core integration.
- Plan structured status/evidence events.
- Plan transitions between natural-language sessions and raw shell sessions.
- Preserve approval boundaries and playbook integration requirements.

**Acceptance Criteria**
- Structured-session boundary is explicit.
- Approval and audit requirements are preserved.

**Dependencies and Notes**
- Parent issue: R1
- Blocking issue: R4

### R6 — Forge Remote Terminal Phase 4 — Production hardening planning
- Template: feature_request.yml
- Native issue type intent: Security
- Suggested labels: `security`, `mobile`, `future`, `backlog`, `infrastructure`
- Priority: Medium
- Repository field: `.github` now; intended future repository: `Forge Remote Terminal`
- Product field: `Forge Remote Terminal`
- Epic field: `R1`
- Phase field: `4`
- Work Type field: `Security`
- Estimated Effort field: `Medium`
- Completion Gate field: Hardening requirements are represented as explicit backlog gates.

**Scope**
- Threat modeling
- Security review
- Firewall policy
- Version pinning
- Reconnection, packet-loss, roaming, and failover testing planning
- Release and rollback procedure planning

**Acceptance Criteria**
- Hardening requirements are represented as explicit backlog gates.

**Dependencies and Notes**
- Parent issue: R1
- Blocking issue: R5

### G1 — Epic — Organization governance follow-up backlog
- Template: feature_request.yml
- Native issue type intent: Epic
- Suggested labels: `epic`, `documentation`, `infrastructure`, `backlog`
- Priority: Medium
- Repository field: `.github`
- Product field: `Organization Foundation`
- Epic field: `none`
- Phase field: `Follow-up`
- Work Type field: `Epic`
- Estimated Effort field: `High`
- Completion Gate field: Child issues separate approval-gated work from repository-safe work.

**Body**
Track approved organization-level follow-up work from foundation planning and assessment without redoing already completed foundation setup.

**Scope**
- Preserve the approved planning scope from the source draft.

**Acceptance Criteria**
- Child issues separate approval-gated work from repository-safe work.

### G2 — Organization follow-up — Repository-by-repository standards adoption planning
- Template: project_task.yml
- Native issue type intent: Documentation
- Suggested labels: `documentation`, `backlog`, `infrastructure`
- Priority: Medium
- Repository field: `.github`
- Product field: `Organization Foundation`
- Epic field: `G1`
- Phase field: `Follow-up`
- Work Type field: `Documentation`
- Estimated Effort field: `Medium`
- Completion Gate field: Rollout ordering, approval points, and rollback notes are documented.

**Scope**
- Plan repository-by-repository rollout of standards, baseline files, and governance expectations.
- Preserve per-repository approval and rollback planning.

**Acceptance Criteria**
- Rollout ordering, approval points, and rollback notes are documented.

**Dependencies and Notes**
- Parent issue: G1

### G3 — Organization follow-up — Actions security baseline rollout planning
- Template: feature_request.yml
- Native issue type intent: Security
- Suggested labels: `security`, `backlog`, `infrastructure`
- Priority: Medium
- Repository field: `.github`
- Product field: `Organization Foundation`
- Epic field: `G1`
- Phase field: `Follow-up`
- Work Type field: `Security`
- Estimated Effort field: `Low`
- Completion Gate field: Actions baseline is converted into an issue with explicit approval needs.

**Scope**
- Plan least-privilege workflow permissions, SHA pinning, fork-secret restrictions, and sensitive workflow review expectations.

**Acceptance Criteria**
- Actions baseline is converted into an issue with explicit approval needs.

**Dependencies and Notes**
- Parent issue: G1

### G4 — Organization follow-up — Security feature enablement review
- Template: feature_request.yml
- Native issue type intent: Security
- Suggested labels: `security`, `backlog`, `documentation`
- Priority: Medium
- Repository field: `.github`
- Product field: `Organization Foundation`
- Epic field: `G1`
- Phase field: `Follow-up`
- Work Type field: `Security`
- Estimated Effort field: `Low`
- Completion Gate field: Approval and plan/billing concerns are explicit before enablement work.

**Scope**
- Review secret scanning, Dependabot alerts, security updates, push protection, code scanning, and private vulnerability reporting applicability and plan requirements.
- Preserve sole-owner recovery-path constraints.

**Acceptance Criteria**
- Approval and plan/billing concerns are explicit before enablement work.

**Dependencies and Notes**
- Parent issue: G1

## Import notes
- Existing issues #1-#5 remain unchanged and should not be duplicated during import.
- The source draft's A1 parent reference says `new Epic A0 below`; use A2 as the actual Forge Arcade epic during import.
- Native GitHub issue type availability may be limited to Task, Bug, and Feature; express Epic, Research, Infrastructure, Security, and Documentation intent through labels and project fields if needed.
- Foundry Development workflow statuses and fields are documented in `/home/runner/work/.github/.github/PROJECT-MANAGEMENT.md` and `/home/runner/work/.github/.github/docs/organization-setup-report-2026-08-03.md`.
