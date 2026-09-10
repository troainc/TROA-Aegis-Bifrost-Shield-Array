# TROA Aegis Bifrost Shield Array roadmap

This roadmap distinguishes implemented beta work from release certification. A feature can be implemented and still not be released until it has passed in-game acceptance testing.

## Current: Reliable Beta acceptance

The private beta contains the core lifecycle, block roles, HUD/LCD, directional gameplay, visuals, sound, and compatibility framework described in the README. The following acceptance work remains before any 1.0 release decision:

### Lifecycle and persistence

- [ ] Clean large-grid Ship Mode test: one Core, no upgrades.
- [ ] Clean small-grid Ship Mode test.
- [ ] Station Mode test: Core + Capacitor Rune + Flux Weave required.
- [ ] Active Core loss, backup-Core promotion, rebuild, and ownership-change tests.
- [ ] Save/reload, reconnect, and late-join snapshot tests.
- [ ] Mechanical-subgrid, connector exclusion, split, and merge conservation tests.
- [ ] Allocation tests at 0%, 50%, 100%, and 200%.

### Combat and presentation

- [ ] Verify each damage family and each tactical profile tradeoff.
- [ ] Verify all six directional banks, reserve use, weak-side warnings, and shunt cooldown.
- [ ] Verify arming, full charge, active recharge, heat, venting, collapse, and reboot states.
- [ ] Verify Suit Induction: friendly/terminal-access authorization, Stable/Recharging-only activation, 2.5% suit charge per second, 20 shield-energy cost per recipient, 3 m fixed clearance, 1000 m maximum, immediate stop on field failure, and no client authority.
- [ ] Verify Station Atmosphere Seal: oxygen and temperature protection inside active station fields; immediate loss on field failure; no Ship Mode activation; 3 m fixed clearance; 500 m maximum; no interaction with player visual bubble settings; and no suppression of combat/physical damage.
- [ ] Verify Bubble, Hybrid, Hull Impact, On Contact, Hidden, opacity, palette, and reduced-flash options.
- [ ] Verify Full and Compact Shield Health HUD modes, hide/show preference, and reconnect persistence.
- [ ] Verify Console LCD `Status`, `Compact`, `Combat`, and `Off` modes.

### Aegis Framework and compatibility

- [ ] Validate the versioned read-only Aegis Framework contract with approved HUD/LCD/mod integrations: construct lookup, state snapshot, directional banks, lifecycle, profile, construct mode, and compatibility status.
- [ ] Verify framework consumers cannot modify shield energy, bypass authorization, or replace server authority.
- [ ] Publish TROA Aegis Visual Framework independently, configure it as an Aegis Workshop Required Item, and verify automatic dependency installation plus mandatory runtime handshake in single-player and hosted multiplayer.

### Compatibility and multiplayer

- [ ] Verify Keen-native handling without WeaponCore installed.
- [ ] Verify compatible WeaponCore monitoring.
- [ ] Verify incompatible or unavailable WeaponCore safely falls back to Keen-native handling.
- [ ] Verify owner, faction, and friendly control authorization server-side.
- [ ] Verify hosted multiplayer controls, status, audio, and visuals for late-joining players.

## 1.0 release certification

A public 1.0 package is gated on all of the following:

- Dedicated-server installation and clean server-log acceptance tests.
- Stress tests with 1, 10, 50, and 100 shielded constructs.
- Performance target: average server shield processing below 0.5 ms and p95 below 2 ms with 50 ordinary constructs.
- Stable memory use and bounded network traffic.
- Final localization-ready player, administrator, API, compatibility, installation, and troubleshooting documentation.
- Full provenance review of every shipped code, model, texture, sound, icon, and marketing asset.
- A reproducible release package built from an authorized tagged private revision.

## Publication policy

Public documentation can be updated throughout beta. Public source, downloadable builds, Workshop content, and release assets will only appear after a separate TROAINC authorization.