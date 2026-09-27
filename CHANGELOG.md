# Changelog

This is a public-facing summary, not a complete source-level record. The private Foundry contains implementation detail. Existing Workshop listings are linked from [STEAM.md](STEAM.md); entries here do not announce a new version or release.

## 2026-09-27 — Private Alpha candidate status

- The private candidate adds configurable safe-field access and repelling options, seal-range and directional-power scaling, live suit-charge telemetry, and updated shield-impact/jump effects.
- Automated validation and package checks pass, but the candidate is not gameplay-certified. In-world and multiplayer checks remain open for weapon interception, field physics, ship/station life support, HUD/LCD synchronization, and effects.
- WeaponCore's current public bridge is observational; shield absorption remains on the authoritative game damage path to avoid duplicate drains. WeaponCore parity still requires in-game confirmation.
- This is not a public release. No source, test package, assets, private logs, or unreleased implementation details are included here.
- Added a public visual guide with an in-game HUD screenshot, labeled block-render previews, and a dedicated page linking both Steam Workshop items and the Realms of Asgard Space Engineers hub.

## 2026-09-26 — Private HUD layout repair candidate

- Updated public status to note the private candidate's fix for the oversized grey HUD panel and overlapping bars: the owned HUD now uses viewport-pixel placement and a bounded top-right composition.
- Private compile and package checks passed; the visual result still needs confirmation in Space Engineers. This is not a public release, and this documentation repository remains source/package-free.

## 2026-09-25 — M4 A1Testing work completed; acceptance pending

- Updated the public project overview to describe the current Aegis modules and the separate Aegis Visual Framework companion.
- Clarified that the top-right Shield Health Integrity Matrix and LCD Matrix are designed to use live shield telemetry, not static sample bars.
- Added the current feature scope: ship/station shields and life-support seal, role-specific blocks, access policy, Bifrost Transit Signature, and framework-owned contact/transit visuals.
- Corrected the verification status: private compile/package checks passed, but oxygen and thermal behavior, damage/projectile blocking, access cases, dynamic HUD/LCD updates, effects, and multiplayer/dedicated behavior still need in-game acceptance.
- Clarified that the Visual Framework is a presentation companion, not the authority for shield protection, and that no external HUD dependency is intended.
- Reaffirmed that this public repository remains documentation-only. Private source and M4 A1Testing ZIPs were not copied here or published by this documentation update.

## Foundation history — summarized

- Defined the TROA Aegis modular shield-system direction and specialized roles for Core/Console, Capacitor Rune, Flux Weave, Harmonic Modulator, and Gjallarhorn Relay.
- Documented directional energy banks, ship/station operation, shield profiles, recharge/heat/venting, authorization, life-support services, and interoperability goals.
- Established the separately packaged Visual Framework as the owner of Aegis HUD and visual presentation, with shield gameplay remaining in the Aegis mod.
- Added documentation for the live Integrity Matrix, LCD output, and informational Bifrost Transit Signature. Their final in-game behavior remains subject to acceptance testing.

## Publication note

This update changed documentation only. Public mod code, downloadable binaries, artwork, private logs, and release staging are not included.
