# FOUNDRY TIC-80 NOTES

Date: 2026-08-04
Purpose: Upstream metadata, safe verification notes, and open questions for
using TIC-80 as a third-party runtime dependency inside Forge Arcade and Forge
Game Workshop.

## Intended external location

Requested upstream clone target:

```text
C:\Foundry\ThirdParty\TIC-80
```

Requested Foundry notes target:

```text
C:\Foundry\ThirdParty\TIC-80-Foundry-Notes
```

Sandbox note: this session cannot write to the Windows path above, so the
upstream repository was cloned only for inspection into a temporary Linux path
and Foundry-side notes were stored in this repository under:

```text
/home/runner/work/.github/.github/docs/third-party/tic80-foundry-notes
```

Temporary inspection clone:

```text
/tmp/foundry-thirdparty/tic80
```

## Related Foundry planning

- Roadmap: `/home/runner/work/.github/.github/docs/third-party/tic80-foundry-notes/FORGE-ARCADE-ROADMAP.md`

Foundry planning must remain separate from upstream TIC-80 facts. TIC-80 is a
contained runtime dependency and cartridge format within Forge Arcade and Forge
Game Workshop, not Forge Core and not Forge itself.

## Dated verification

Verification date: 2026-08-04

## Upstream metadata

- Repository URL: `https://github.com/nesbox/TIC-80`
- Upstream remote: `origin https://github.com/nesbox/TIC-80.git`
- Current branch: `main`
- Current commit: `4aba09c98f1e5028b82765be1647677b08d35942`
- Current nearest tag: none on the inspected shallow clone
- Version declared in source: `1.2.0-dev` (`cmake/version.cmake`)
- License: `LICENSE` plus additional third-party license files under `LICENSES`
- Approximate repository size: `18M` on disk
- Approximate tracked file count: `423`
- Worktree status: clean

## Upstream capabilities observed from current materials

Upstream documentation and repository contents indicate TIC-80 currently
provides:

- A fantasy-console runtime for making, playing, and sharing tiny games
- Portable cartridge packaging
- Built-in editors for code, sprites, maps, sound, and music
- Keyboard and mouse input
- Up to 4 controllers with up to 8 buttons each
- Multiple scripting languages including Lua, Moonscript, JavaScript, Ruby,
  Wren, Fennel, Squirrel, Janet, and Python
- Community demos across several languages under `demos/`
- Compiled-language WebAssembly templates under `templates/`

## Supported platform notes from upstream materials

Upstream documentation explicitly references or implies support/build guidance
for:

- Windows
- Linux
- macOS
- FreeBSD
- Android
- iOS / tvOS
- Raspberry Pi environments

Forge planning should treat these as upstream support claims to verify again
before production decisions.

## Useful upstream demos and templates

Examples currently present in the inspected clone include:

- Lua demos such as `demos/luademo.lua`, `demos/tetris.lua`, and `demos/quest.lua`
- Multi-language bunny benchmark demos under `demos/bunny/`
- Additional demos for JavaScript, Python, Fennel, Wren, Janet, Ruby, Scheme,
  Moonscript, and WASM
- Compiled templates under `templates/` for Zig, D, C, Rust, and Nim-oriented
  starter materials

## Build prerequisites observed upstream

From upstream README and CMake files, TIC-80 build materials currently expect or
reference:

- C and C++ toolchains
- `cmake`
- `make`
- `git`
- `ruby` / `ruby-dev`
- SDL2
- OpenGL / GLU / related graphics libraries
- `libcurl`
- Wayland and PipeWire development packages on some Linux paths
- Additional platform-specific prerequisites for Windows, macOS, FreeBSD,
  Android, and Raspberry Pi environments

## Local tool availability in this sandbox

| Tool or dependency | Status |
|---|---|
| `cmake` | Present |
| `gcc` | Present |
| `g++` | Present |
| `make` | Present |
| `git` | Present |
| `ruby` | Present |
| `pkg-config` | Present |
| `unzip` | Present |
| `sdl2` pkg-config entry | Missing |
| `gl` pkg-config entry | Missing |
| `glu` pkg-config entry | Missing |
| `libcurl` pkg-config entry | Missing |
| `wayland-client` pkg-config entry | Missing |
| `pipewire-0.3` pkg-config entry | Missing |

## Safe verification result

A full safe verification build was **not** performed because the currently
available sandbox toolchain is missing several upstream build prerequisites,
including SDL2 and graphics/network development packages referenced by upstream
build instructions. This is not a task failure under the stated constraints.

## Official links

- Website: <https://tic80.com>
- Repository: <https://github.com/nesbox/TIC-80>
- Releases: <https://github.com/nesbox/TIC-80/releases>
- Actions: <https://github.com/nesbox/TIC-80/actions?query=branch%3Amain>
- Wiki: <https://github.com/nesbox/TIC-80/wiki>
- Community play portal: <https://tic80.com/play>
- F-Droid package page: <https://f-droid.org/packages/com.nesbox.tic/>

## Open questions and risks

- Which exact upstream release or commit should Foundry pin for first evaluated
  production use?
- Which TIC-80 scripting languages should Foundry support initially beyond a
  Lua-first target?
- What telemetry convention can expose enough state for automated playtesting
  without weakening isolation boundaries?
- What cartridge size, runtime, CPU, memory, and storage limits are appropriate
  for Forge Arcade celebrations?
- How should imported third-party cartridges be reviewed, approved, and
  attributed before entering the Arcade library?
- What threat model should govern generated cartridges, screenshots, and
  playtest artifacts?

## Personal notes

- Preserve this section for future human observations, manual experiments, and
  subjective impressions gathered outside strict upstream verification.
