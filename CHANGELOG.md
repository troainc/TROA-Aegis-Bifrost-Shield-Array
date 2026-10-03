# Changelog

This is a public summary of documentation and private candidate development, **not a Workshop release announcement** or source-level change history. “Current” below means the private Alpha candidate as of September 27, 2026; the public Workshop builds may be older. Use the [Workshop pages](README.md#get-aegis) for downloadable release contents and compatibility.

## Current work — September 26–27, 2026

### September 27 — Shield settings, field filters, services, and impact feedback

- **Core filter editor:** replaced numeric player/faction ID boxes and separate repel toggles with a named Whitelist/Blacklist editor. The supported categories are Players, Factions, Grids, and Floating Objects. The unsupported Other Entities category—including voxel maps—was removed; legacy `AllowedOtherEntityIds` data is retained but ignored.
- **Immediate filter refresh:** changing filter mode/category and using Add/Remove refreshes the available/configured lists in the open terminal. Players do not need to exit and re-enter the block screen.
- **Automatic Push/Pull:** the server applies the supported access policy to players, grids, and floating objects at the field boundary. The boundary is configurable up to 200 m and increased coverage raises Core demand. Faction membership contributes to access decisions; generic physical objects are not included.
- **Seal and Thermal services:** the candidate exposes a separately configurable 0–200 m seal clearance for powered oxygen and bounded thermal protection. Wider service range increases power use; the seal range is distinct from the push/pull field range.
- **Suit Charge:** Suit Induction reads player suit energy using the supported game API and transfers from shield reserve only when field, access, reserve, and service conditions permit.
- **Directional power:** six face allocations remain independently adjustable; increasing directional weighting raises Core demand. The configured seal and field-range multipliers also contribute to demand.
- **Weapon handling:** vanilla shield absorption remains on one authoritative damage callback. WeaponCore selection is supplemental/read-only hit observation, not a second shield drain and not a promise that the public WeaponCore bridge can cancel damage.
- **Shield-hit effect:** client presentation adds a layered absorption pulse and short flash so shield contact is more apparent. Effects are visual-only and do not control damage absorption.

### September 27 — Jump/drive signatures and GPS alerts

- **Jump event:** a loaded grid with a jump drive is recorded after an observed displacement of at least 1 km. Bounded strength factors include grid size, physical mass, and observed displacement.
- **Drive Signature:** measured current thrust acts as a heat-output proxy, scales with hull/output within a cap, and refreshes only while thrust continues. It is not actual engine-temperature telemetry.
- **Detection reach and retention:** working/broadcasting Aegis receiver antenna ranges add custom Aegis detection reach (up to a 125 km antenna bonus, 250 km total cap). Recent signatures remain visible for up to three minutes. These are mod rules, not vanilla antenna signature scanning.
- **Jump GPS:** players within 10 km of the grid's last-known position receive a targeted persistent GPS marker and HUD confirmation. Same-location duplicates are suppressed. Live multiplayer radius, notification, and persistence testing remains outstanding.
- **Website map boundary:** no Realms of Asgard website map upload is connected. An authenticated ingest contract and privacy-safe location rules are still required; no player coordinates are sent externally.

### September 26 — HUD, status, and visual framework

- Refined the radial shield HUD to keep the six directional percentages and overall shield value aligned with their corresponding areas; the center reports total shield status.
- Separated overall shield percentage from the AEGIS SHIELDS operating-state ring. Right-rail service values and status labels are centered/aligned, and the Jump Detection panel uses a more visible animated wave.
- Improved HUD scaling/contrast and retained live runtime values rather than baking values into the art. Heat/shield values continue to come from telemetry.
- Added a more visible client-side Heimdall-style rainbow jump pathway and shield absorption pulse. The Visual Framework remains a read-only presentation layer.
- Full screen-resolution, panel, reload, and multiplayer acceptance remains open; screenshots/design previews are not proof of all runtime states.

### Validation and release status (September 26–27)

The private candidate passes automated model and XML checks, game-assembly compilation, 33 deterministic tests, and package-integrity validation. There are still in-game and multiplayer acceptance tasks for damage/WeaponCore coverage, filter persistence and pushback, service range and power, HUD/LCD synchronization, jump GPS notifications, and dedicated-server performance. Automated validation must not be represented as gameplay certification. No new Workshop release is announced by this changelog.

## Legacy history — through September 25, 2026

The foundation notes below are **legacy milestones**, retained for historical context. They are superseded by the current candidate summary above and do not describe the complete current feature set or guarantee that a feature is present in a Workshop build.

### September 25 — Project foundation (legacy)

- Established the ship/station shield concept, directional banks, modular hardware roles, service concepts, LCD output, and separate Visual Framework.
- Documented the responsibility boundary: shield mod owns gameplay authority; companion framework owns presentation and client-only effects.
- Established that compile/package checks are development evidence, not gameplay certification.

## Public repository boundary

This repository contains approved public documentation and selected preview images only. It does not contain mod source, downloadable builds, private Alpha packages, test worlds, private logs, or release staging.

## Documentation update - 2026-10-03

- Added a documentation landing page that directs players to the current Workshop instructions and server owners to the system overview, operational limits, and candidate validation notes.
