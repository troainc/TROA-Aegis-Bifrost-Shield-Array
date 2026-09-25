# Changelog

All public project updates are recorded here. This changelog describes capabilities and acceptance status; it does not distribute private code, binaries, models, sounds, or production files.

## Unreleased

### Full graphical Integrity Matrix

- Replaced the private-beta text-and-frame treatment with the original Aegis **Integrity Matrix**: a complete graphical, no-text player HUD rendered by the required TROA Aegis Visual Framework.
- The matrix presents live segmented wells for fore, aft, port, starboard, dorsal, ventral, heat margin, thermal stabilization, atmosphere seal, and suit-induction service. A direction ring, change rails, Jump Detection scan band, and Bifrost transit lamp provide visual state without a text overlay.
- The player HUD remains cosmetic and local. Its expanded read-only visual data cannot alter shield energy, life support, suit charging, jump drives, damage, controls, or other players' displays.
- Source, production art files, packaged builds, and implementation details remain private; this repository documents expected behavior only.

### Live Integrity Matrix instrumentation

- The private-beta top-right Integrity Matrix now fills its authored instrument wells from read-only shield telemetry: total field health, six directional banks, heat, and power allocation.
- Field and directional bars communicate usable protection with cyan, warning with gold, and critical depletion with red. Heat uses its own rising-risk color route; power has a distinct blue route. These meters are player-local presentation only.
- The Aegis shield bubble remains an independently textured field effect. HUD bar rendering cannot replace or alter that field material.

### Integrity Matrix session-lifecycle repair

- Corrected an internal private-beta lifecycle issue where the engine initialized the required Visual Framework HUD renderer but could omit a separate bridge component. The read-only Integrity Matrix bridge now starts inside the confirmed live framework session.
- The repair retains the intended player-facing route: one original Aegis top-right HUD panel, live read-only shield telemetry, no external HUD Workshop dependency, and no centre-screen text fallback.
- Runtime acceptance remains pending a fresh in-game load that records the framework bridge, telemetry, renderer, and live shield-snapshot markers. This public repository continues to contain documentation only.

### Graphical Integrity Matrix and Bifrost Detector

- Replaced the provisional text-only private-beta shield telemetry treatment with the original Aegis **top-right Integrity Matrix**: circular integrity focus, segmented field meter, six directional bank meters, heat/power diagnostics, and a compact system rail.
- Extended the read-only HUD telemetry contract to v3 while retaining v2 compatibility. The additional visual-only fields report Bifrost Transit Signature state, jump distance, signature class, detection range, and remaining lifetime.
- Added the live **Bifrost Detector** rail. It displays `SCAN CLEAR` outside an event and presents temporary Local, Departure, or Arrival alert data for qualifying Jump Drive signatures. It remains cosmetic and cannot alter Jump Drive operation or shield authority.
- Folded the owned text-HUD render service into the required TROA Aegis Visual Framework. Private testing no longer requires a separate HUD Workshop item; the public repository remains documentation-only.
- Corrected private-beta HUD material loading and isolated its internal registration channel from the framework readiness signal. The shield bubble retains its original textured field presentation rather than a flat fallback color.

### Native Visual Framework Shield Health HUD

- Replaced the optional external-loader route with a native client session renderer included in the required Aegis Visual Framework.
- The Shield Health panel is rendered at the top-right from read-only telemetry. The intrusive centre-screen notification fallback is intentionally disabled.
- Reworked the panel onto the supported Text HUD API render surface after the game rejected direct custom GUI calls from a regular mod. The Visual Framework retains ownership of Aegis telemetry, layout, colors, and its GUI asset; no source or external assets are published here.

### Bifrost Transit Signature

- Added the private-beta **Bifrost Transit Signature** feature: a server-authoritative, read-only indicator for loaded vanilla jump-drive displacements of at least 1 km within 50 km of an active Aegis construct.
- Signature traces are temporary (15 seconds) and appear as Local, Departure, or Arrival events with jump distance on Console Status, Combat LCD, and the Shield Health HUD.
- The feature never modifies Jump Drive operation, shield energy, damage, authorization, or player identity. The public repository remains documentation-only.
- Routed the private-beta transit pulse through the required Aegis Visual Framework's dedicated presentation material while retaining gameplay detection and authority in the shield runtime.
- Added physical grid-size scaling: a 25 m-radius hull establishes the 1.0× / 50 km baseline; larger jumping grids create proportionally larger pulses and stronger signatures, capped at 2.5× / 125 km.
- Added **Bifrost Wake Dust** presentation: a short cyan/violet particle wake at departure and arrival that is client-only, bounded, size-scaled, and governed by each player's Hidden and reduced-flash preferences. It supplies no gameplay authority.
- Added **Bifrost Jump Wave** presentation: a bounded multi-shell surge at both jump endpoints. Departure contracts violet-to-cyan and arrival expands cyan-to-violet; the effect shares the required Visual Framework material route, scales by grid signature class, respects accessibility preferences, and never modifies vanilla Jump Drive behavior.

### Real-time Shield Health HUD

- Moved the private-beta exact-position Shield Health renderer into the required Visual Framework boundary. It draws a compact top-right panel every client update while consuming a versioned, read-only snapshot at four updates per second.
- The Full layout documents field state, charge percentage/current/maximum energy, heat, power allocation, tactical profile, compatibility route, six directional banks, last-hit pressure, shunt cooldown, Ship/Station mode, and Station Mode seal status.
- The HUD remains cosmetic and player-local. It has no state-changing endpoint and cannot modify shield energy, damage, lifecycle, authorization, jump behavior, or another player's display.

### Protection reliability and per-block power controls

- Repaired the private-beta server protection path to resolve both normal block and cube-block damage callbacks before directional-bank absorption. A charged, powered Aegis field now spends shield energy before protected grid blocks receive that damage.
- Decoupled visual-framework message timing from authoritative shield operation. The Visual Framework remains a required packaged/Workshop companion, but a delayed presentation handshake can no longer turn an otherwise valid field into pass-through protection.
- Added a visible **Aegis module enabled** control and matching toolbar toggle to every functional Aegis role. Disabling a block removes only its specific contribution: Core capacity/recharge, Capacitor reserve, Flux recharge/station requirement, Harmonic tuning, Relay coverage/reinforcement, or Console access.

### Direct player access

- Documented the all-block interaction correction: players can aim at the visible surface of Core, Console, Capacitor Rune, Flux Weave, Harmonic Modulator, or Gjallarhorn Relay blocks to open their terminal rather than being routed to a top-side interaction point.
- This preserves role-specific Aegis controls while retaining standard Space Engineers functional-block controls on every block.

### Ship and Station life-support seal

- Expanded the active Aegis life-support system to both construct modes. Ships provide O₂, ambient thermal protection, and authorized Suit Induction only within live grid bounds plus 10 m; stations retain their Core + Capacitor Rune + Flux Weave requirement and 3 m / 500 m station envelope.
- Added a safe retry for engine oxygen-provider registration after world load, preventing an otherwise valid active field from missing the seal because the game oxygen service started later than Aegis.
- Clarified that Suit Induction uses the same active life-support envelope, charges authorized players by 2.5% per second, costs 20 shield energy per recipient per second, and never affects hostile/unauthorized players or combat damage.

### Role-specific controls

- Replaced cloned Aegis controls with distinct block roles: Core/Console administer the construct; Capacitor Rune changes actual reserve-bank capacity; Flux Weave changes only its recharge/power allocation and vents; Harmonic Modulator owns profile/tuning; Gjallarhorn Relay owns coverage/facings.
- Moved player-local HUD, sound, presentation, color/RGB, opacity, bubble-presentation, and reduced-flash preferences to Bifrost Console only. Every Aegis block retains native Space Engineers functional-block controls.

### Roadmap refinement

- Expanded Reliable Beta acceptance coverage for Bifrost Console/external LCD recovery and routing, Suit Induction authorization/energy/range behavior, atmosphere-seal interaction, late join, and dedicated-server validation.
- Clarified that the public repository remains documentation-only unless TROAINC separately authorizes source publication.
### Aegis Suit Induction

- Added friendly-only wireless suit charging inside an active Aegis field. It is server-authoritative, bounded to the real field envelope, requires player access to the construct, runs only in Stable/Recharging state, and consumes shield energy per recipient.
- The beta uses the supported server-side Visual Script player-energy API, defaults to 2.5% suit charge and 20 shield energy per recipient each second, and stops on field failure, venting, collapse, or reboot.
### Console LCD mode control

- Added a Bifrost Console terminal selector for Status, Compact, Combat, and Off; each mode now has a distinct output path.
- Hardened external LCD mode parsing for whitespace, UTF-8 BOMs, and either equals or colon separators, preventing valid mode changes from silently displaying Status.

### LCD reliability

- External same-construct LCDs now accept either the documented `[TROA Aegis LCD]` Custom Data section or an `[Aegis LCD]` panel-name tag. A valid route with no explicit mode defaults safely to Status instead of remaining blank.
- Added a permanent private validation gate for Bifrost Console TextPanel registration and external LCD routing. — Reliable Beta

### Station thermal stabilization

- Extended the active station Atmosphere Seal to cancel only environment temperature/freeze/cold damage for characters inside the field. Combat, collision, fall, tool, and other damage remain unchanged.

### Station Atmosphere Seal

- Added a bounded, station-only Aegis Atmosphere Seal. Active Station Mode shields provide breathable oxygen inside their real field envelope while required station hardware, power, and Visual Framework support remain online.
- The life-support envelope uses station geometry plus a fixed 3 m clearance and a 500 m maximum. Cosmetic bubble preferences cannot alter oxygen gameplay range; oxygen tanks and ordinary airtight rooms retain their normal behavior.

### Required Visual Framework dependency

- Made **TROA Aegis Visual Framework** a mandatory Aegis companion. The shield remains OFFLINE and does not provide protection until the framework is installed, enabled, and replies to its runtime handshake.
- Added the Steam release requirement: the framework will be published separately and configured as an Aegis Workshop Required Item before an authorized public package is released.

### TROA Aegis Foundation and interoperability

- Documented the custom TROA Aegis Foundation: a private, server-authoritative shield platform with distinct runtime, visual-framework, HUD, validation, and release-staging boundaries.
- Added the documented direction for a versioned, read-only Aegis Framework interface. Authorized integrations will be able to discover shield construct identity, readiness, lifecycle, charge, energy, directional-bank state, profile, Ship/Station mode, and compatibility status without scraping the terminal UI.
- Defined the framework security boundary: normal integrations and clients never receive direct authority to consume, restore, duplicate, or modify shield energy. State-changing controls remain server-validated with standard ownership/faction/friendly checks.
- Documented the optional TROA Aegis Visual Framework companion. It supplies TROA-owned presentation material paths while Aegis gameplay remains operational with safe fallback visuals when it is not present.
- Confirmed that this repository remains a detailed public information hub only. It contains no private source, binaries, packages, art masters, test worlds, or release staging material.


### Shield lifecycle and construct hardware

- Added active/backup Aegis Core election: one fully functional Core provides capacity while additional working Cores act as hot backups.
- Added automatic backup promotion when the elected Core is lost or disabled.
- Added Ship Mode and Station Mode detection. Ships require one Core; stations require Core + Capacitor Rune + Flux Weave.
- Added actionable Console diagnostics for Core, Capacitor, Flux, Harmonic, Relay, active field state, power allocation, and construct mode.
- Corrected false OFFLINE transitions caused by valid power/control changes.

### Tactical defense

- Added seven conserved energy banks: fore, aft, port, starboard, dorsal, ventral, and reserve.
- Added 0.5×–2× directional reinforcement with a two-second shunt cooldown.
- Added Balanced, Kinetic, Energy, Explosive, Collision, and Utility profiles with explicit tradeoffs.
- Added 0% standby, normal recharge, emergency reinforcement, heat, venting, collapse, and reboot states.
- Added optional Harmonic Modulator tuning and Gjallarhorn Relay collapse recovery support.

### Player experience

- Added personal Shield Health HUD with state badge, charge ring, current/max energy, heat, profile, construct mode, framework status, directional banks, last-hit facing, and incoming pressure.
- Added player-local HUD show/hide and Full/Compact layout settings.
- Added Bubble, Hybrid, Hull Impact, On Contact, and Hidden visual modes; palette, opacity, and reduced-flash preferences remain personal.
- Added original shield audio state feedback and rate-limited impact presentation.
- Added Bifrost Console LCD Custom Data modes: `Status`, `Compact`, `Combat`, and `Off`.

### Networking, security, and compatibility

- Added server-authoritative snapshots, stale-packet rejection, late-join recovery, and validated control requests.
- Added persisted/synchronized active-Core state, shunt cooldown, hit direction, damage pressure, and framework status.
- Added Auto, Keen Vanilla, and optional WeaponCore Bridge choices. WeaponCore absence or incompatibility safely falls back to Keen-native protection.
- Added owner/faction/friendly block-access validation for remote control requests.

### Validation status

- Private package, XML, runtime compile, protocol, deterministic shield, audio, model-boundary, and terminal-control validation gates pass.
- In-game single-player, hosted multiplayer, and dedicated-server acceptance remain release gates; see [ROADMAP.md](ROADMAP.md).
