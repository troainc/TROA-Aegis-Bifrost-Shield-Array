# TROA Aegis Bifrost Shield Array roadmap

This roadmap separates **implemented in the private Alpha candidate** from **accepted in a running game** and **released on Steam**. These are different states. Automated compile/package checks do not close gameplay acceptance, and private Alpha work does not change the public Workshop version.

## Status checkpoint — 2026-09-27

The private Foundry candidate includes the shield, field-policy, service, HUD/LCD, and signature systems summarized in the [README](README.md). Its automated validation passes, including model/XML checks, game-assembly compilation, 33 deterministic tests, and package validation. No new public release is announced.

## Acceptance work before release

### Shield lifecycle and combat

- [ ] Verify ship and station setup requirements, module discovery, ownership changes, backup-Core promotion, and recovery after a Core is removed or rebuilt.
- [ ] Verify persistence through save/reload, reconnect, and late join; test mechanical subgrids, connectors, splits, merges, and conservation of stored energy.
- [ ] Apply controlled hits to all six facings. Confirm the corresponding shield bank drains before protected grid integrity changes.
- [ ] Test supported damage families, projectiles/missiles, depleted banks, offline fields, overload, recharge, heat, venting, and reboot.
- [ ] Verify Keen vanilla weapons without WeaponCore and separately test WeaponCore projects. Confirm no duplicate drain and document any unsupported projectile path.
- [ ] Confirm shield-hit visuals and audio follow absorption state and remain presentation-only.

### Field filter and power

- [ ] Exercise every supported filter category (Players, Factions, Grids, Floating Objects) in Whitelist and Blacklist modes. Other Entities and voxel maps are not filter categories.
- [ ] Test adding/removing named entries, offline entities, persistence, owner/admin access, and late-join synchronization.
- [ ] Test Automatic Push/Pull and boundary settings at 0, 10, 100, and 200 m for characters, grids, and physical objects. Confirm field crossings and performance.
- [ ] Confirm larger field range and directional reinforcement settings increase Core power demand as documented.
- [ ] Do not expose shooting, drilling, welding, grinding, building, projection, voxel, damage, or landing-gear Safe Zone switches until each has a verified server-authoritative enforcement path.

### Life-support services

- [ ] Test Seal oxygen support and Thermal protection in pressurized/unpressurized rooms on ships and stations.
- [ ] Verify each service stops immediately when the field loses power, shuts down, or runs out of shield energy.
- [ ] Test the configured 0–200 m clearance and corresponding power demand without exceeding the documented envelope.
- [ ] Verify Suit Induction authorization, reserve-energy cost, charge rate, no-power behavior, and stop conditions.

### HUD, LCD, and framework

- [ ] Verify all six percentages, overall shield percentage, heat, READY/ARMING/OFFLINE state, service indicators, and jump text update without reopening the HUD or LCD.
- [ ] Check text size, alignment, scaling, clipping, and contrast at common resolutions and UI scales.
- [ ] Verify LCD Status, Compact, Combat, Matrix, and Off modes. Test full panels, 4×3 two-tile layouts, tile alignment, refresh cadence, reload, and surface selection.
- [ ] Verify `HUD=Off` suppresses only the local presentation and restores properly.
- [ ] Confirm delayed Visual Framework startup or failure cannot disable authoritative shield gameplay.

### Jump detection and player GPS

- [ ] Verify a loaded grid with a jump drive produces a signature only after observed displacement of at least 1 km; normal thrust must not create a jump event.
- [ ] Confirm bounded jump strength changes with hull size, physical mass, and observed displacement; test the independent active-thrust Drive Signature behavior.
- [ ] Verify signature visibility/expiry and receiver-range limits with multiple Aegis constructs and late-joining players.
- [ ] In multiplayer, test players inside and outside the 10 km GPS radius. Confirm only eligible players receive a persistent, HUD-visible marker and notification.
- [ ] Repeat the same event/location and confirm the GPS marker is not duplicated. Verify marker persistence after reconnect/reload.

## Future integration work

- **Realms Map:** no map publisher is connected. First establish the website's supported ingest endpoint, authentication, rate limits, pin precision/privacy rules, retention, deduplication, and pause/clear behavior. Keep credentials outside the game mod.
- **Safe Zone parity:** evaluate additional action permissions only after documenting and testing a reliable server-authoritative hook for each action.
- **Release operations:** complete dedicated-server tests, load/performance tests, compatibility review, final operator/player documentation, asset/provenance review, and a reproducible authorized release build before announcing any new version.

## Public release policy

The Steam Workshop pages are authoritative for released builds. This repository remains documentation-only unless TROAINC separately authorizes publishing code or downloadable packages.
