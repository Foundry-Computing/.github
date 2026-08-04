# FOUNDRY MOSH NOTES

Date: 2026-08-04
Purpose: Upstream metadata, safe verification notes, and open questions for
using Mosh as a third-party transport dependency in Forge Remote Terminal.

## Intended external location

Requested upstream clone target:

```text
C:\Foundry\ThirdParty\Mosh
```

Requested Foundry notes target:

```text
C:\Foundry\ThirdParty\Mosh-Foundry-Notes
```

Sandbox note: this session cannot write to the Windows path above, so the
upstream repository was cloned only for inspection into a temporary Linux path
and Foundry-side notes were stored in this repository under:

```text
/home/runner/work/.github/.github/docs/third-party/mosh-foundry-notes
```

Temporary inspection clone:

```text
/tmp/foundry-thirdparty/mosh
```

## Upstream metadata

- Repository URL: `https://github.com/mobile-shell/mosh`
- Upstream remote: `origin https://github.com/mobile-shell/mosh.git`
- Current branch: `master`
- Current commit: `decd9b705eb81626f694335b8d5940538beb06da`
- Commit summary: `Addressing last review comments`
- Current tag: `mosh-1.4.0`
- License: GNU GPL v3 (`COPYING`)
- Approximate repository size: `4.7M` on disk
- Approximate tracked file count: `254`
- Worktree status: clean

## Build prerequisites observed upstream

From upstream README and configure logic, Mosh expects or references:

- C++ build toolchain
- `make`
- `autoconf`
- `automake`
- `pkg-config`
- `protobuf` compiler and development libraries
- `zlib`
- `ncurses`
- OpenSSL or another supported crypto backend
- `libutempter` on systems where utmp integration is desired
- `perl` for client-side packaging/use cases noted upstream

## Local tool availability in this sandbox

| Tool or dependency | Status |
|---|---|
| `g++` | Present |
| `make` | Present |
| `autoconf` | Present |
| `automake` | Present |
| `pkg-config` | Present |
| `perl` | Present |
| `openssl` pkg-config entry | Present |
| `ncurses` pkg-config entry | Present |
| `libutempter` runtime library | Present |
| `protoc` | Missing |
| `protobuf` pkg-config entry | Missing |

## Safe verification result

A full safe verification build was **not** performed because required protobuf
build prerequisites were missing in the current environment. This is not a task
failure under the stated constraints.

## Supported platform notes from upstream materials

Upstream documentation explicitly references or implies support/build guidance
for:

- GNU/Linux
- FreeBSD
- macOS / OS X
- Windows Subsystem for Linux
- Fedora / RHEL build environments
- Debian-family build environments

## Network and firewall notes

- Mosh establishes its initial connection through SSH.
- It then runs `mosh-server` on the remote host and switches the session to
  UDP.
- By default, upstream documentation says Mosh uses UDP ports in the
  `60000-61000` range unless a specific port is selected.
- Forge should never expose this broad range publicly by default; the long-term
  model should keep it behind a private network and approved gateway policy.

## Relevant upstream links

- Website: <https://mosh.org>
- Repository: <https://github.com/mobile-shell/mosh>
- Usage docs: <https://mosh.org/#usage>
- FAQ: <https://mosh.org/#faq>
- Getting packages/build info: <https://mosh.org/#getting>
- CI workflow badge target: <https://github.com/mobile-shell/mosh/actions/workflows/ci.yml>

## Open questions and risks

- Which exact upstream commit or release should Foundry pin for first evaluation?
- What narrowed UDP policy is acceptable for Forge mobile use cases?
- How should Forge expose SSH bootstrap and Mosh fallback decisions to users?
- What device enrollment and credential boundary should exist between Forge and
  shell transports?
- What audit events are required when a user transitions from a Forge session to
  an Open shell session?
