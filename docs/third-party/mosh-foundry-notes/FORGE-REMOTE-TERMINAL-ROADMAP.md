# FORGE REMOTE TERMINAL ROADMAP

Status: Planning only
Date: 2026-08-04
Upstream transport dependency: `https://github.com/mobile-shell/mosh`
Foundry notes location: `/home/runner/work/.github/.github/docs/third-party/mosh-foundry-notes`

## Core design principle

> **Forge Remote Terminal provides the experience; Mosh provides resilient mobile shell transport.**

Mosh is a transport dependency within Forge Remote Terminal. It is not the
entire product, not the Forge protocol, and not a repository Foundry intends
to rename or tightly fork. Foundry should preserve Mosh as an upstream-tracked
third-party dependency and keep all Foundry-specific architectural decisions in
separate documentation and Foundry-owned repositories.

## Reference architecture

```text
Forge Remote Terminal
├── Forge mobile and desktop interface
├── Device enrollment and identity
├── Session manager
├── Approval and audit layer
├── Terminal renderer
├── Forge structured session protocol
└── Transport adapters
    ├── Mosh
    ├── SSH
    └── Future transports
```

## What Mosh provides

- Resilient interactive terminal sessions
- Session recovery after temporary connection loss
- Support for roaming between Wi-Fi and cellular networks
- Better usability under latency, packet loss, or unstable connections
- Predictive local echo
- A strong fit for mobile devices such as the Zebra TC57
- A preferred transport for interactive shell sessions when UDP is available

## What Mosh does not provide

- Forge identity or persona
- Device enrollment
- Forge approvals
- Command authorization
- Structured Forge events
- Session history and audit records
- File transfer
- Port forwarding
- Customer or technician workflow logic
- Forge playbooks
- Natural-language interaction
- A complete replacement for SSH

## Transport strategy

```text
User Device
    ↓
Forge Remote Terminal
    ↓
Transport selection
    ├── Mosh for resilient interactive shell sessions
    ├── SSH as universal fallback
    └── Forge session API for structured assistant interactions
```

Design expectations:

- Mosh should be preferred for interactive mobile terminal sessions when
  supported.
- SSH must remain fully supported.
- SSH is required for compatibility, bootstrap, file transfer, port forwarding,
  and environments where UDP is blocked.
- Forge's natural-language and structured assistant features must not depend on
  terminal screen scraping.
- Forge sessions and raw shell sessions are separate but interoperable
  experiences.

## Raw shell vs Forge session

### Raw shell session

A conventional remote terminal session to Linux, FreeBSD, or another supported
host.

Example:

```text
r2d2@forge-server:~ $
```

Mosh or SSH may provide this transport.

### Forge session

A structured conversational interface where the user can ask Forge to inspect,
explain, or propose actions.

Example:

```text
User:
Check why the backup failed.
Forge:
The destination volume became read-only at 02:14.
[View evidence]
[Open shell]
[Run recovery playbook]
```

Mosh supports the **Open shell** path. Forge's own protocol handles structured
conversations, evidence, approvals, status events, and playbook execution.

## Networking and security model

```text
TC57 or other client
    ↓
Tailscale or WireGuard private network
    ↓
Narrow approved UDP port range
    ↓
Forge access gateway
    ↓
Target host
```

Requirements:

- Do not expose a broad Mosh UDP range publicly unless explicitly approved.
- Prefer operation over Tailscale or another private encrypted network.
- Maintain SSH fallback when UDP is unavailable.
- Keep Mosh behind a Forge transport abstraction.
- Pin the selected upstream version or commit.
- Review upstream security history and open issues before production use.
- Do not store Forge credentials inside the Mosh layer.
- Do not grant Mosh direct authority to approve or execute privileged Forge
  actions.
- All high-risk Forge operations must still pass through Forge policy and
  approval controls.

## Long-term roadmap

### Phase 0 — Research and Preparation

- Clone and preserve upstream Mosh.
- Record current branch, commit, version, license, and repository status.
- Review supported operating systems.
- Review build prerequisites.
- Review firewall and UDP requirements.
- Review upstream maintenance activity and security history.
- No integration work.

### Phase 1 — Transport Abstraction

- Define a Forge Remote Terminal transport interface.
- Add SSH as the baseline transport.
- Add Mosh as an optional transport adapter.
- Keep transport choice invisible to the user where possible.
- Add automatic fallback from Mosh to SSH.

### Phase 2 — Device and Session Management

- Enroll trusted devices.
- Add session discovery and reconnect behavior.
- Add secure credential handling.
- Add session metadata and audit events.
- Add TC57-focused interface work.

### Phase 3 — Forge Session Integration

- Connect terminal sessions to Forge Core.
- Add structured status and evidence events.
- Allow transitions between natural-language Forge sessions and raw shell
  sessions.
- Preserve approval boundaries.
- Add playbook integration.

### Phase 4 — Production Hardening

- Security review
- Threat modeling
- Firewall policy
- Version pinning
- Reconnection testing
- Network-roaming testing
- Packet-loss testing
- Failover testing
- Release and rollback procedures
