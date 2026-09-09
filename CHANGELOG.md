# Changelog

All public project updates are recorded here. This changelog describes capabilities and acceptance status; it does not distribute private code, binaries, models, sounds, or production files.

## Unreleased — Reliable Beta

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