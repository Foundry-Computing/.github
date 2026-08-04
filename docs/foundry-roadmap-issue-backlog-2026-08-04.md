# Foundry Roadmap Issue Backlog Draft

Date: 2026-08-04
Repository: `/home/runner/work/.github/.github`
Purpose: Convert approved Foundry planning artifacts in this repository into a
reviewable GitHub Issue backlog draft without implementing features.

## Existing issues reviewed

| Issue | Title | Assessment |
|---|---|---|
| #1 | Forge Core Phase 2A — Client API HTTP/SSE transport | Existing implementation-tracking issue; preserve as-is |
| #2 | Forge Core Phase 2B — PowerShell Forge Client API transport | Existing implementation-tracking issue; preserve as-is |
| #3 | forge-vscode Phase 0/1A — Extension foundation and Forge Client API integration | Existing implementation-tracking issue; preserve as-is |
| #4 | GitHub Organization Foundation — Foundry governance and project setup | Existing organizational epic; preserve as-is |
| #5 | FORGE Phase 1A — Local Coding Fleet Foundation | Existing architecture/feature issue; preserve as-is |

No existing issue duplicates the roadmap-driven planning work below.

## Proposed issue creation set

### Epic 1 — Forge Arcade planning backlog

#### Proposed issue A1

**Title**: Forge Arcade Phase 0 — TIC-80 research, metadata pinning, and runtime boundary review

- Type: Research
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `documentation`, `research`, `forge`, `future`, `backlog`
- Parent issues: new Epic A0 below
- Blocking issues: none
- Related issues: none

**Summary**
Establish the approved Phase 0 research baseline for TIC-80 as a contained
runtime dependency inside Forge Arcade and Forge Game Workshop.

**Motivation**
Forge Arcade planning requires a verified third-party runtime baseline before
any integration or implementation work is scheduled.

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

**Dependencies**
- Repositories: `.github` (temporary planning home), future `Foundry-Forge-Arcade`
- Notes: `/home/runner/work/.github/.github/docs/third-party/tic80-foundry-notes/FORGE-ARCADE-ROADMAP.md`

---

#### Proposed issue A2

**Title**: Epic — Forge Arcade Phase 1-7 planning backlog

- Type: Epic
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: High
- Estimated Size: L
- Labels: `epic`, `forge`, `future`, `backlog`, `architecture`
- Parent issues: none
- Blocking issues: none
- Related issues: A1, A3-A9

**Summary**
Track the approved long-term Forge Arcade and Forge Game Workshop roadmap as a
single planning epic with child issues for each major phase.

**Motivation**
The approved roadmap should be represented as executable backlog structure
without prematurely expanding into implementation tasks.

**Scope**
- Track approved phases for library/launcher, celebrations, workshop,
  playtesting, idle creative mode, milestone archive, and hardening.
- Preserve architectural boundaries between Forge, Forge Arcade, Forge Game
  Workshop, and TIC-80.
- Maintain child issue ordering and dependency structure.

**Out of Scope**
- Production implementation.
- Runtime execution, asset generation, or cartridge publishing.

**Acceptance Criteria**
- Child planning issues exist for each approved roadmap phase.
- Dependency order reflects the roadmap.
- Intended destination repository is recorded.

**Dependencies**
- Related docs: `/home/runner/work/.github/.github/docs/third-party/tic80-foundry-notes/FORGE-ARCADE-ROADMAP.md`

---

#### Proposed issue A3

**Title**: Forge Arcade Phase 1 — Arcade library, launcher, and cartridge approval planning

- Type: Feature
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Medium
- Estimated Size: L
- Labels: `enhancement`, `forge`, `ui`, `future`, `backlog`
- Parent issues: A2
- Blocking issues: A1
- Related issues: A4-A9

**Scope**
- Catalog approved `.tic` cartridges.
- Store metadata and hashes.
- Plan controlled runtime launching.
- Plan score and play-history tracking.
- Plan manual import and approval workflow.

**Acceptance Criteria**
- Planning issue defines approval workflow, metadata expectations, and launcher
  boundaries.
- Architecture notes distinguish trusted metadata handling from runtime
  execution.

---

#### Proposed issue A4

**Title**: Forge Arcade Phase 2 — Achievement celebrations planning

- Type: Feature
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `enhancement`, `forge`, `persona`, `future`, `backlog`
- Parent issues: A2
- Blocking issues: A3

**Scope**
- Define normalized achievement events.
- Define reusable celebration templates and celebration tiers.
- Plan approved event-source integration boundaries.
- Plan mute, postpone, replay, and accessibility controls.

**Acceptance Criteria**
- Tiered celebration model is represented in backlog.
- External sensitive systems remain indirect event sources only.

---

#### Proposed issue A5

**Title**: Forge Game Workshop Phase 3 — Cartridge creation workflow planning

- Type: Feature
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Medium
- Estimated Size: L
- Labels: `enhancement`, `forge`, `future`, `backlog`, `architecture`
- Parent issues: A2
- Blocking issues: A4

**Scope**
- Plan natural-language game planning.
- Plan Lua-first cartridge project generation.
- Plan asset generation, static validation, manifests, and approval submission.

**Acceptance Criteria**
- Workshop planning captures generation, validation, and approval boundaries.
- Issue explicitly treats generated cartridges as untrusted artifacts.

---

#### Proposed issue A6

**Title**: Forge Game Workshop Phase 4 — Automated playtesting planning

- Type: Research
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `research`, `forge`, `future`, `backlog`, `architecture`
- Parent issues: A2
- Blocking issues: A5

**Scope**
- Plan isolated TIC-80 execution.
- Plan simulated controller input and screenshot capture.
- Plan telemetry conventions, crash/hang detection, and playtest reports.

**Acceptance Criteria**
- Telemetry assumptions are documented as future research.
- Isolation and hostile-code assumptions remain explicit.

---

#### Proposed issue A7

**Title**: Forge Arcade Phase 5 — Idle Creative Mode policy planning

- Type: Security
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `security`, `forge`, `future`, `backlog`, `documentation`
- Parent issues: A2
- Blocking issues: A6

**Scope**
- Plan resource budgets, scheduling controls, private draft handling, and review
  queue behavior for idle cartridge creation.
- Preserve the approved non-interruption and privacy constraints.

**Acceptance Criteria**
- Budget, privacy, and approval constraints are explicit.
- No implementation work is scheduled beyond planning.

---

#### Proposed issue A8

**Title**: Forge Arcade Phase 6 — Milestone archive and replay planning

- Type: Feature
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Low
- Estimated Size: M
- Labels: `enhancement`, `forge`, `future`, `backlog`
- Parent issues: A2
- Blocking issues: A7

**Scope**
- Plan permanent playable achievement scrapbook behavior.
- Plan versioned cartridge preservation, migration, backup, and replay.

**Acceptance Criteria**
- Archive, migration, and replay expectations are documented in backlog form.

---

#### Proposed issue A9

**Title**: Forge Arcade Phase 7 — Production hardening and open-source readiness planning

- Type: Security
- Repository: `.github` now; intended future repository: `Foundry-Forge-Arcade`
- Milestone: Future
- Priority: Medium
- Estimated Size: L
- Labels: `security`, `architecture`, `future`, `backlog`, `forge`
- Parent issues: A2
- Blocking issues: A8

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
- Hardening and release-readiness gates are explicit and separate from feature
  implementation.

### Epic 2 — Forge Remote Terminal planning backlog

#### Proposed issue R1

**Title**: Epic — Forge Remote Terminal roadmap planning backlog

- Type: Epic
- Repository: `.github` now; intended future repository: `Forge Remote Terminal`
- Milestone: Future
- Priority: High
- Estimated Size: L
- Labels: `epic`, `future`, `backlog`, `mobile`, `infrastructure`, `architecture`

**Summary**
Represent the approved Forge Remote Terminal roadmap as a planning epic with
phase-ordered child issues.

**Acceptance Criteria**
- Child planning issues exist for each approved phase.
- Mosh remains an upstream-tracked dependency, not the product boundary.

**Notes**
- Related doc: `/home/runner/work/.github/.github/docs/third-party/mosh-foundry-notes/FORGE-REMOTE-TERMINAL-ROADMAP.md`

---

#### Proposed issue R2

**Title**: Forge Remote Terminal Phase 0 — Mosh research and transport boundary review

- Type: Research
- Repository: `.github` now; intended future repository: `Forge Remote Terminal`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `research`, `mobile`, `future`, `backlog`, `documentation`
- Parent issues: R1

**Scope**
- Preserve upstream Mosh.
- Record version, branch, license, and prerequisites.
- Review supported operating systems, firewall needs, and security history.
- Preserve the transport abstraction boundary.

**Acceptance Criteria**
- Upstream transport research is documented.
- Security and firewall concerns are explicit.

---

#### Proposed issue R3

**Title**: Forge Remote Terminal Phase 1 — Transport abstraction planning

- Type: Infrastructure
- Repository: `.github` now; intended future repository: `Forge Remote Terminal`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `infrastructure`, `mobile`, `future`, `backlog`
- Parent issues: R1
- Blocking issues: R2

**Scope**
- Define transport interface.
- Plan SSH baseline and optional Mosh adapter.
- Plan fallback behavior and user-visible transport handling.

**Acceptance Criteria**
- Transport abstraction and fallback requirements are explicit.

---

#### Proposed issue R4

**Title**: Forge Remote Terminal Phase 2 — Device and session management planning

- Type: Feature
- Repository: `.github` now; intended future repository: `Forge Remote Terminal`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `enhancement`, `mobile`, `future`, `backlog`
- Parent issues: R1
- Blocking issues: R3

**Scope**
- Plan device enrollment.
- Plan session discovery, reconnect, credential handling, and audit metadata.
- Plan TC57-focused interface work.

**Acceptance Criteria**
- Session management and audit requirements are captured.

---

#### Proposed issue R5

**Title**: Forge Remote Terminal Phase 3 — Forge session integration planning

- Type: Feature
- Repository: `.github` now; intended future repository: `Forge Remote Terminal`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `enhancement`, `forge`, `mobile`, `future`, `backlog`
- Parent issues: R1
- Blocking issues: R4

**Scope**
- Plan Forge Core integration.
- Plan structured status/evidence events.
- Plan transitions between natural-language sessions and raw shell sessions.
- Preserve approval boundaries and playbook integration requirements.

**Acceptance Criteria**
- Structured-session boundary is explicit.
- Approval and audit requirements are preserved.

---

#### Proposed issue R6

**Title**: Forge Remote Terminal Phase 4 — Production hardening planning

- Type: Security
- Repository: `.github` now; intended future repository: `Forge Remote Terminal`
- Milestone: Future
- Priority: Medium
- Estimated Size: M
- Labels: `security`, `mobile`, `future`, `backlog`, `infrastructure`
- Parent issues: R1
- Blocking issues: R5

**Scope**
- Threat modeling
- Security review
- Firewall policy
- Version pinning
- Reconnection, packet-loss, roaming, and failover testing planning
- Release and rollback procedure planning

**Acceptance Criteria**
- Hardening requirements are represented as explicit backlog gates.

### Epic 3 — Organization and governance follow-up backlog

#### Proposed issue G1

**Title**: Epic — Organization governance follow-up backlog

- Type: Epic
- Repository: `.github`
- Milestone: Backlog
- Priority: Medium
- Estimated Size: L
- Labels: `epic`, `documentation`, `infrastructure`, `backlog`

**Summary**
Track approved organization-level follow-up work from foundation planning and
assessment without redoing already completed foundation setup.

**Acceptance Criteria**
- Child issues separate approval-gated work from repository-safe work.

---

#### Proposed issue G2

**Title**: Organization follow-up — Repository-by-repository standards adoption planning

- Type: Documentation
- Repository: `.github`
- Milestone: Backlog
- Priority: Medium
- Estimated Size: M
- Labels: `documentation`, `backlog`, `infrastructure`
- Parent issues: G1

**Scope**
- Plan repository-by-repository rollout of standards, baseline files, and
  governance expectations.
- Preserve per-repository approval and rollback planning.

**Acceptance Criteria**
- Rollout ordering, approval points, and rollback notes are documented.

---

#### Proposed issue G3

**Title**: Organization follow-up — Actions security baseline rollout planning

- Type: Security
- Repository: `.github`
- Milestone: Backlog
- Priority: Medium
- Estimated Size: S
- Labels: `security`, `backlog`, `infrastructure`
- Parent issues: G1

**Scope**
- Plan least-privilege workflow permissions, SHA pinning, fork-secret
  restrictions, and sensitive workflow review expectations.

**Acceptance Criteria**
- Actions baseline is converted into an issue with explicit approval needs.

---

#### Proposed issue G4

**Title**: Organization follow-up — Security feature enablement review

- Type: Security
- Repository: `.github`
- Milestone: Backlog
- Priority: Medium
- Estimated Size: S
- Labels: `security`, `backlog`, `documentation`
- Parent issues: G1

**Scope**
- Review secret scanning, Dependabot alerts, security updates, push protection,
  code scanning, and private vulnerability reporting applicability and plan
  requirements.
- Preserve sole-owner recovery-path constraints.

**Acceptance Criteria**
- Approval and plan/billing concerns are explicit before enablement work.

## Duplicate avoidance notes

- Existing issues #1-#5 were preserved and not duplicated.
- No implementation issue was proposed for future repositories beyond planning
  scope.
- Forge Arcade, Forge Game Workshop, and Forge Remote Terminal items remain
  planning issues because their implementation repositories are future-facing.

## Open ambiguities for human review

- The current `.github` repository labels do not yet include many labels named
  in the problem statement, such as `architecture`, `security`, `research`,
  `infrastructure`, `epic`, `mobile`, `forge`, `future`, `backlog`, `ui`, and
  `persona`.
- The current visible issue type catalog exposes `Task`, `Bug`, and `Feature`;
  other requested types may need to be expressed via labels instead of native
  issue types.
- The visible issue fields expose Priority and Effort, but Effort currently uses
  `High`, `Medium`, `Low` rather than `XS/S/M/L/XL`.
- No direct issue-create or issue-update tool is available in this environment,
  so this file serves as the backlog conversion draft for human import or later
  automation.
