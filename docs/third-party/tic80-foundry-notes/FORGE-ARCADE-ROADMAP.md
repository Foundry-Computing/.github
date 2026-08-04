# FORGE ARCADE ROADMAP

Status: Planning only
Date: 2026-08-04
Upstream runtime dependency: `https://github.com/nesbox/TIC-80`
Foundry notes location: `/home/runner/work/.github/.github/docs/third-party/tic80-foundry-notes`

## Core design principle

> **Forge provides the creativity, personality, achievement logic, safety controls, and experience; TIC-80 provides the contained fantasy-console runtime and cartridge format.**

Forge uses TIC-80 as a contained fantasy-console runtime and creative tool within Forge Arcade and Forge Game Workshop. TIC-80 is not Forge itself, not part of Forge Core, and not a repository Foundry intends to rename or tightly fork.

Forge does not create games merely to occupy itself. Forge uses games, animations, music, and interactive cartridges to celebrate the user, commemorate milestones, experiment creatively, and invite shared play.

## Reference architecture

```text
FORGE
├── Forge Core
├── Forge personality and conversation systems
├── Forge policy, approvals, and audit systems
├── Forge achievement and event system
│
└── Forge Arcade
    ├── Arcade library and launcher
    ├── Achievement celebration system
    ├── Cartridge catalog
    ├── Player profiles and scores
    │
    └── Forge Game Workshop
        ├── Game design planner
        ├── TIC-80 cartridge generator
        ├── Asset generator
        ├── Static validator
        ├── Playtest harness
        ├── Telemetry adapter
        └── Isolated TIC-80 runtime
```

## What TIC-80 provides

- A compact fantasy-console runtime
- Portable `.tic` cartridges
- Built-in code, sprite, map, sound, and music editors
- A constrained retro-game environment
- Support for several scripting languages
- A practical Lua-first development target
- Keyboard and controller input
- A suitable runtime for short achievement celebrations
- A suitable format for small games, interactive doodles, keepsakes, and milestone cartridges
- Cross-platform potential for Windows, Linux, FreeBSD, and mobile-oriented environments where supported
- A strong platform for deterministic, resource-limited creative experiments

## What TIC-80 does not provide

- Forge identity or personality
- Achievement detection
- Habitica integration
- Banking or financial event logic
- GitHub milestone detection
- User approval workflows
- Idle-work scheduling
- Resource-budget enforcement
- Secure process containment
- Malware guarantees
- Cartridge trust decisions
- Forge memory
- Publishing governance
- Long-term cartridge metadata and audit history
- Natural-language game design
- Automated playtesting by itself
- A complete security boundary against hostile generated code

## Forge Arcade vs Forge Game Workshop

### Forge Arcade

The user-facing experience for:

- Browsing approved cartridges
- Launching games
- Viewing achievements
- Replaying milestone celebrations
- Tracking scores and unlocks
- Receiving invitations from Forge to play
- Maintaining a personal interactive scrapbook of accomplishments

### Forge Game Workshop

The controlled creation and testing environment for:

- Designing small games
- Generating cartridge source and assets
- Running validation
- Performing automated playtests
- Reviewing telemetry
- Preparing celebration cartridges
- Submitting creations for approval
- Refining games based on user feedback

Forge Arcade is the showroom and play space. Forge Game Workshop is the secured workshop where cartridges are built and tested.

## Achievement celebration system

```text
Achievement source
    ↓
Forge achievement normalizer
    ↓
Celebration policy
    ↓
Celebration template or custom cartridge
    ↓
Approval and safety checks
    ↓
Forge Arcade
    ↓
Playable celebration
```

Potential achievement sources include:

- GitHub pull request merged
- Repository release published
- Version 1.0 completion gate reached
- Certification passed
- Customer milestone
- Positive review received
- Important bill or debt milestone
- Habitica level-up or quest completion
- Workout or routine milestone
- Foundry business milestone
- Personal dates and celebrations explicitly permitted by the user

External systems should emit normalized achievement events. TIC-80 must not directly access banking, Gmail, GitHub credentials, Habitica credentials, calendars, or other sensitive systems.

## Celebration tiers

### Tier 1 — Micro Celebration

- Approximately 3–10 seconds
- Sprite animation
- Short chiptune
- Achievement title
- Minimal or no player input

Examples:

- Test suite passed
- Daily task streak
- Small GitHub milestone

### Tier 2 — Interactive Celebration

- Approximately 30 seconds to 3 minutes
- Simple playable sequence
- One mechanic
- Score or collectible
- Personalized Forge dialogue

Examples:

- Pull request merged
- Customer review
- Monthly goal completed

### Tier 3 — Milestone Cartridge

- Approximately 3–15 minutes
- Permanent keepsake
- Multiple scenes or mechanics
- Custom art and music
- Archived in the user’s milestone library

Examples:

- Certification earned
- First Foundry customer
- Major debt paid off
- Product reaches Version 1.0
- Major career milestone

## Idle creative mode

Forge may eventually create or refine cartridges during explicitly permitted idle periods, but only under policy controls.

Required conditions:

- Idle creative mode is enabled by the user
- No active user request
- No urgent Forge job
- System load is below a configured threshold
- Power and battery conditions permit it
- Daily or weekly resource budget remains
- Storage budget remains
- Network access is disabled unless explicitly required and approved
- Generated output remains private and unpublished
- Creation cannot interrupt critical business operations

Example policy:

```text
Idle Creative Budget
- Maximum new cartridges: 2 per week
- Maximum refinement sessions: 3 per week
- Maximum wall-clock time per session: configurable
- Maximum CPU and memory use: configurable
- Default language: Lua
- Network access: disabled
- Publishing: requires explicit approval
```

These limits are future requirements only and are not implemented by this task.

## Security and containment model

Generated cartridges must be treated as untrusted code, even when Forge generated them.

```text
TRUSTED ZONE
- Forge Core
- Credentials
- User data
- Achievement sources
- Approval and audit systems
RESTRICTED BUILD ZONE
- Cartridge source generation
- Asset generation
- Static validation
- Build tooling
- Test fixtures
DISPOSABLE RUNTIME ZONE
- TIC-80 execution
- Automated playtesting
- Screenshots and telemetry
- Crash and timeout handling
```

Required future controls:

- Dedicated cartridge directories
- No access to Forge credentials
- No direct access to user documents
- No direct access to Foundry business data
- No unrestricted network access
- CPU, memory, storage, and runtime limits
- Maximum cartridge size
- Static checks before execution
- Automatic termination of hangs
- Crash capture
- Disposable test environments where practical
- Hashing and provenance records
- Approval before publication or external sharing
- Version pinning for TIC-80
- Security review of TIC-80 language/runtime features
- Clear distinction between “no known issue detected” and “safe”

## Cartridge provenance and metadata

Each Forge-created or imported cartridge should eventually have a manifest containing:

- Cartridge ID
- Title
- Version
- Author or generator
- Creation timestamp
- Last modified timestamp
- Source achievement or prompt
- TIC-80 version
- Programming language
- Source hash
- Cartridge hash
- Assets used
- Forge model/provider used
- Playtest status
- Validation status
- Approval status
- Publication status
- Required permissions
- Runtime limits
- Known issues
- Rollback or previous version reference

This roadmap documents the schema concept only.

## Automated playtesting

```text
Forge Game Workshop
    ↓
Launch isolated TIC-80 runtime
    ↓
Capture structured game state where available
    ↓
Send simulated controller input
    ↓
Observe score, state, screenshots, crashes, and completion
    ↓
Generate playtest report
```

For Forge-created cartridges, a future optional telemetry convention may resemble:

```lua
FORGE_STATE = {
    scene = "level_1",
    score = 120,
    player_x = 42,
    player_y = 78,
    lives = 3,
    objective_complete = false,
    game_over = false
}
```

The exact telemetry mechanism requires later technical research and must not assume unrestricted host access from the cartridge.

## User experience

Intended experiences include:

- Forge invites the user to play a new creation.
- Achievement celebrations remain brief unless the user opens the full cartridge.
- Celebrations can be muted, postponed, or disabled.
- Business-critical workflows are never blocked by a celebration.
- The user can replay milestone cartridges later.
- The user can rate games or provide feedback.
- Forge can learn broad game preferences from explicit feedback.
- Forge should not generate manipulative or excessive engagement loops.
- Forge should celebrate the user rather than pressure the user.

> **Celebration should feel like a gift, not an interruption.**

## Future integrations

Ideas only:

- Forge achievement service
- Habitica
- Foundry GitHub projects and releases
- Foundry Banking milestone events
- Foundry Workspace
- Forge notifications
- Forge mobile application
- Forge Remote Terminal
- Foundry Training Range
- Personal milestone calendar events
- Foundry desktop widgets

No external integration is implemented during this task.

## Repository and dependency strategy

- Keep `C:\Foundry\ThirdParty\TIC-80` pristine and aligned with upstream.
- Do not place Foundry code inside the TIC-80 repository.
- Record and pin the selected upstream commit or release for production use.
- Prefer upstream contributions for generally useful fixes.
- Avoid maintaining a permanent incompatible fork.
- Place future Forge Arcade code in a separate Foundry repository.
- Place cartridge data and user-created content outside the application repository.
- Keep generated games separate from trusted Forge source code.
- Maintain clear licensing and attribution records.

Potential future repository name: `Foundry-Forge-Arcade`

This is a planning suggestion only. Do not create the repository unless separately instructed.

## Long-term roadmap

### Phase 0 — Research and Play

- Preserve the upstream clone.
- Record current metadata.
- Install or use an official prebuilt release separately.
- Play community cartridges.
- Learn the editors.
- Create small manual experiments.
- Record observations in Foundry notes.
- Review runtime and security boundaries.
- No Forge integration.

### Phase 1 — Arcade Library and Launcher

- Catalog approved `.tic` cartridges.
- Store metadata and hashes.
- Launch cartridges through a controlled runtime.
- Add basic score and play-history tracking.
- Add manual import and approval workflow.

### Phase 2 — Achievement Celebrations

- Define normalized achievement events.
- Create reusable celebration templates.
- Add micro celebrations and short interactive sequences.
- Connect approved Foundry event sources.
- Add mute, postpone, replay, and accessibility controls.

### Phase 3 — Forge Game Workshop

- Add natural-language game planning.
- Generate Lua-first cartridge projects.
- Generate sprites, maps, sound effects, and music.
- Add static validation.
- Add versioned cartridge projects and manifests.
- Submit generated work for user approval.

### Phase 4 — Automated Playtesting

- Add isolated execution.
- Add simulated controller inputs.
- Add screenshot and telemetry capture.
- Detect crashes, hangs, impossible states, and regressions.
- Generate playtest reports.
- Support Forge-controlled second-player behavior.

### Phase 5 — Idle Creative Mode

- Add resource-budgeted idle creation.
- Add policy controls and schedules.
- Add private drafts.
- Add user review queue.
- Prevent interruption of business-critical work.

### Phase 6 — Milestone Archive

- Build a permanent playable achievement scrapbook.
- Preserve versioned cartridges.
- Connect milestone cartridges to project history.
- Support migration and backup.
- Support replay across future Forge hosts.

### Phase 7 — Production Hardening and Open Source

- Threat modeling
- Security review
- Runtime hardening
- Accessibility review
- Licensing review
- Reproducible builds
- Backup and restore
- Plugin or SDK boundaries
- Public documentation
- Open-source release planning
