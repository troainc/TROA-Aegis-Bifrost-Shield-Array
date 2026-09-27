# TROA Aegis Bifrost Shield Array

TROA Aegis Bifrost Shield Array is an original Space Engineers shield-system project with [Steam Workshop listings](STEAM.md). This repository is a public information hub only; it does not contain mod source, downloadable builds, production assets, or private test material. The Workshop pages are authoritative for currently available versions; private Alpha work described below may not be present in those public items.

## Current project status — 2026-09-27

The private Foundry now has a paired Alpha test candidate for the shield mod and its companion **TROA Aegis Visual Framework**. Recent work adds configurable Core access/field policies, power costs tied to seal range and directional settings, live player suit-charge display, and stronger shield-hit/jump presentation. Automated model, XML, package, deterministic, and game-assembly checks pass. The candidate still needs disposable-world and multiplayer acceptance for shield damage, WeaponCore/vanilla parity, field pushback, life-support range, HUD/LCD behavior, and visual effects. No public Workshop release is announced here; this repository remains documentation-only.

## Planned and implemented system areas

- Ship and Station shield operation with directional protection and separate energy reserves.
- Role-focused blocks: Core/Console for administration; Capacitor Rune for reserve power; Flux Weave for recharge and emergency venting; Harmonic Modulator for profile/tuning; Gjallarhorn Relay for coverage and directional reinforcement.
- Configurable access and field policy for players, factions, grids, items, and selected physical entities; exact behavior remains subject to live acceptance.
- Ship/station Atmosphere Seal and thermal stabilization, with adjustable seal reach and optional authorized suit charging.
- Live player Shield Health Integrity Matrix and opt-in LCD matrix output, driven by shield telemetry rather than static sample values.
- **Bifrost Transit Signature**, which reports observed jump-drive grid displacement. It does not control or predict Jump Drive behavior.
- The Visual Framework companion supplies the Aegis-owned HUD presentation materials and client-side contact/transit effects. It is not gameplay authority.

Feature descriptions above reflect private Alpha implementation and intent; oxygen/thermal behavior at configured ranges, projectile interception, safe-field edge cases, power draw, LCD/HUD response, effects, and multiplayer behavior require in-game acceptance before they should be considered release-ready.

## Block roles

- **Aegis Core / Bifrost Console:** overall field administration and diagnostics.
- **Capacitor Rune:** energy reserve allocation.
- **Flux Weave:** recharge allocation and emergency venting.
- **Harmonic Modulator:** shield profile and automatic tuning.
- **Gjallarhorn Relay:** coverage and facing reinforcement.

Each block retains its native Space Engineers On/Off and visibility controls. Module settings are specialized rather than duplicated across every block.

## Visual guide

The hardware images below are rendered design previews of the Aegis block family. The HUD image is an in-game screenshot showing live shield, heat, service, jump-detection, and AEGIS shield-state readouts.

### Aegis HUD in game

![TROA Aegis shield HUD in Space Engineers](docs/images/aegis-hud-in-game.png)

The center of the radial display shows overall shield percentage. Six colored sectors and their labels show directional shield strength; the lower bar shows heat-shield level. The right-side indicators show Thermal, Seal, Suit Charge, Jump Detection, and AEGIS Shields state.

### Shield-system hardware

| Block | What it does | Preview |
| --- | --- | --- |
| Aegis Core | Owns the shield field, overall administration, and diagnostics. | <img src="docs/images/aegis-core.png" alt="Aegis Core rendered preview" width="180"> |
| Bifrost Console | Provides a player-facing console for field status and administration. | <img src="docs/images/bifrost-console.png" alt="Bifrost Console rendered preview" width="180"> |
| Capacitor Rune | Adds reserve energy for shield operation. | <img src="docs/images/capacitor-rune.png" alt="Capacitor Rune rendered preview" width="180"> |
| Flux Weave | Supports shield recharge allocation and emergency venting. | <img src="docs/images/flux-weave.png" alt="Flux Weave rendered preview" width="180"> |
| Harmonic Modulator | Provides shield profile and automatic-tuning controls. | <img src="docs/images/harmonic-modulator.png" alt="Harmonic Modulator rendered preview" width="180"> |
| Gjallarhorn Relay | Extends coverage and supports directional reinforcement. | <img src="docs/images/gjallarhorn-relay.png" alt="Gjallarhorn Relay rendered preview" width="180"> |

These previews illustrate the block designs; they are not in-game screenshots. Feature behavior and release readiness remain subject to the acceptance gates above.

## Repositories and release policy

The private Foundry is the implementation source of truth and contains all code, art, test evidence, and unreleased packages. This public repository is limited to approved documentation and public-facing status. Do not treat private package names or local validation as an authorized Workshop release.

## Project documentation

- [Roadmap](ROADMAP.md) — milestones and acceptance gates.
- [Changelog](CHANGELOG.md) — dated user-facing project changes.
- [Contributing](CONTRIBUTING.md) — repository workflow.
- [License](LICENSE.md) and [security policy](SECURITY.md).
- [Steam Workshop and website](STEAM.md) — Workshop listings and more information about the project.
