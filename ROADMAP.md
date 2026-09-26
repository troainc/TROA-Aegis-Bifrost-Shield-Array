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

- [ ] Verify each damage family and each tactical profile tradeoff, including both normal SlimBlock and CubeBlock damage callback paths; a charged, powered field must debit its bank before grid integrity falls.
- [ ] Verify Bifrost Transit Signature with local, departing, and arriving vanilla jump-drive grids: 1 km threshold; 25 m-radius 1.0× / 50 km baseline; bounded 2.5× / 125 km large-grid scaling; 15-second expiry; Console/Combat LCD/HUD output; late-join snapshot; bounded client-only Bifrost Wake Dust plus Bifrost Jump Wave at departure/arrival respecting Hidden/reduced-flash; and no change to Jump Drive behavior or shield energy.
- [ ] Verify all six directional banks, reserve use, weak-side warnings, and shunt cooldown.
- [ ] Verify arming, full charge, active recharge, heat, venting, collapse, and reboot states.
- [ ] Verify Suit Induction through the supported Visual Script player-energy API: friendly/terminal-access authorization, Stable/Recharging-only activation, 2.5% suit charge per second, 20 shield-energy cost per recipient, immediate stop on field failure, and no client authority. Verify ship induction is constrained to live grid bounds plus 10 m and station induction uses the active station envelope.
- [ ] Verify Aegis Life-Support Seal: oxygen and temperature protection in active Ship and Station fields; immediate loss on field failure; Ship Mode limited to live grid bounds plus 10 m; Station Mode requiring Core + Capacitor + Flux and limited to 3 m clearance / 500 m maximum; no interaction with player visual bubble settings; and no suppression of combat/physical damage.
- [ ] Verify role-specific terminal and toolbar controls: Core/Console master administration, Capacitor reserve allocation, Flux recharge/venting, Harmonic profile/tuning, Relay coverage/facings, Console-only personal presentation, native Space Engineers functional-block controls, and the explicit module On/Off switch on every Aegis block.
- [ ] Verify direct player interaction on the visible surface of every Core, Console, Capacitor Rune, Flux Weave, Harmonic Modulator, and Gjallarhorn Relay variant; no terminal interaction may require aiming at an inaccessible top-side point.
- [ ] Verify Bubble, Hybrid, Hull Impact, On Contact, Hidden, opacity, palette, and reduced-flash options.
- [ ] Verify Full and Compact Shield Health HUD modes, hide/show preference, top-right Text HUD API presentation, Ship/Station telemetry, six-bank/pressure/shunt display, reconnect persistence, and no client-to-server control authority. The central notification fallback is retired.
- [ ] Verify Bifrost Console LCD always renders its construct state and its terminal LCD Mode selector switches outputs, and external same-construct LCD routing works through `[TROA Aegis LCD]` Custom Data on every vanilla/modded text-surface provider. Verify `Status`, `Compact`, `Combat`, `Matrix`, and `Off`; blank/default recovery; 10 Hz Matrix redraw; controlled-hit bank drops; smooth recharge/service recovery; reload; late join; no cross-construct output; whole-Matrix scale fitting on 3×3, 5×3, and 5×5; `Surface=` selection; the two-panel 4×3 `Tile=1/2` + `Tile=2/2` join; and local-only `HUD=Off` suppression/restoration.

### Aegis Framework and compatibility

- [ ] Validate the versioned read-only Aegis Framework contract with approved HUD/LCD/mod integrations: construct lookup, state snapshot, directional banks, lifecycle, profile, construct mode, and compatibility status.
- [ ] Verify framework consumers cannot modify shield energy, bypass authorization, or replace server authority.
- [ ] Publish TROA Aegis Visual Framework independently, configure it as an Aegis Workshop Required Item, and verify automatic dependency installation plus visual readiness in single-player and hosted multiplayer. A delayed presentation handshake must never affect authoritative field arming or damage interception.

### Compatibility and multiplayer

- [ ] Verify Keen-native handling without WeaponCore installed.
- [ ] Verify compatible WeaponCore monitoring.
- [ ] Verify incompatible or unavailable WeaponCore safely falls back to Keen-native handling.
- [ ] Verify owner, faction, and friendly control authorization server-side.
- [ ] Verify hosted multiplayer controls, status, audio, visuals, Console/LCD routing, and Suit Induction for late-joining players.

## 1.0 release certification

A public 1.0 package is gated on all of the following:

- Dedicated-server installation and clean server-log acceptance tests.
- Stress tests with 1, 10, 50, and 100 shielded constructs.
- Performance target: average server shield processing below 0.5 ms and p95 below 2 ms with 50 ordinary constructs.
- Stable memory use and bounded network traffic.
- Final localization-ready player, administrator, API, compatibility, installation, and troubleshooting documentation.
- Full provenance review of every shipped code, model, texture, sound, icon, and marketing asset.
- A reproducible release package built from an authorized tagged private revision, with the public repository remaining documentation-only unless TROAINC separately authorizes source publication.

## Publication policy

Public documentation can be updated throughout beta. Public source, downloadable builds, Workshop content, and release assets will only appear after a separate TROAINC authorization.
