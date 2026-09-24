# TROA Aegis Bifrost Shield Array

**TROA Aegis Bifrost Shield Array** is an original Nordic sci-fi shield system being built for **Space Engineers** by **TROAINC**. It is designed around understandable ship defense, meaningful power and heat choices, directional damage management, and multiplayer-safe server authority.

> **Current status: private reliable-beta acceptance testing.**
>
> This public repository is the official project information hub. It intentionally contains no source code, binaries, mod packages, test worlds, unreleased models, textures, sounds, or production files. TROAINC will announce an authorized public release when acceptance testing is complete.

## What players can expect

Aegis is not intended to be a magic “invulnerable ship” switch. A working shield is a managed defensive system:

- Energy is split between **fore, aft, port, starboard, dorsal, ventral, and reserve** banks.
- A weak side can fail before the entire field does.
- Higher power allocation improves recharge but adds heat; emergency operation can force a vent.
- Shield profiles have advantages and tradeoffs instead of universal immunity.
- A collapse requires recovery before the shield can return to service.
- The server remains authoritative for protection, energy, controls, and player permission checks.

## Core gameplay loop

1. Build and power an **Aegis Core** on your ship or station.
2. Add a **Bifrost Console** for command controls, diagnostics, HUD preferences, and LCD status output.
3. Select a power allocation, tactical profile, field coverage, and directional reinforcement.
4. Watch shield charge, heat, incoming pressure, and bank health through the player HUD or Console/LCD.
5. Adapt: reinforce a threatened side, change profile, vent heat, or allow the system to recharge.

## Block roles

| Block | Purpose |
| --- | --- |
| **Aegis Core** | Required shield projector. Establishes baseline capacity and recharge. One Core is elected active; additional working Cores are hot backups rather than duplicate capacity. |
| **Bifrost Console** | Command authority, live diagnostics, LCD routing, framework selection, and the sole player-local HUD/presentation settings surface. |
| **Capacitor Rune** | Adds stored-energy reserve. Its 5–50% reserve allocation changes the actual reserve-bank capacity. Required for a station field. |
| **Flux Weave** | Its independent 0–200% allocation changes Flux recharge output and its own power draw; it also provides emergency venting. Required for a station field. |
| **Harmonic Modulator** | Owns shield profile selection and deterministic automatic tuning from recent incoming damage. |
| **Gjallarhorn Relay** | Owns Main Grid/Mechanical Construct coverage and directional reinforcement; also improves collapse recovery. |

Large and small variants are planned where the block role supports them.

### Direct player access

Every Aegis functional block can be opened directly by aiming at its visible
surface and using the normal Space Engineers terminal interaction. This avoids
an inaccessible top-side interaction point while preserving each block's
role-specific Aegis controls and native On/Off, ownership, terminal-list, HUD,
name, and toolbar controls. Every role also exposes an explicit **Aegis module
enabled** switch and a matching toolbar toggle, so players can intentionally
take an individual Core, Console, Capacitor, Flux, Harmonic, or Relay offline.

## Ship and Station behavior

Aegis detects construct mode automatically:

- **Ship Mode** — a movable grid needs one fully built, enabled Aegis Core.
- **Station Mode** — a fixed grid needs a fully built, enabled Aegis Core, Capacitor Rune, and Flux Weave. Stations receive a larger capacity envelope with a deliberately slower recharge calibration.

Mechanical subgrids can be covered as one construct. Connector-docked grids remain excluded by default so visiting ships are not silently absorbed into a field.

### Aegis Life-Support Seal and Suit Induction

An active Aegis field provides a bounded life-support seal: breathable O₂, ambient temperature/freeze/cold protection, and authorized wireless suit induction. It is server-authoritative, runs only while the field is Stable or Recharging, requires the same gameplay hardware as protection, and never follows player-local visual bubble settings. The required Visual Framework provides the packaged visual experience, but a delayed visual readiness message cannot disable server-side protection.

- **Ships:** one powered Core enables life support only inside the construct’s live grid bounds plus **10 m**.
- **Stations:** powered Core + Capacitor Rune + Flux Weave enable life support within the real station geometry plus **3 m**, capped at **500 m**.

Suit Induction uses the supported server-side Visual Script player-energy API. Authorized players receive 2.5% suit energy per second while the field spends 20 shield energy per player each second. Unauthorized or hostile players cannot receive induction, and all life support stops when the field is down, venting, collapsed, or rebooting. The seal does not refill oxygen tanks or replace normal airtight-room mechanics. Weapon, collision, fall, tool, and all other damage remain unchanged.

## Shield states

| State | Meaning |
| --- | --- |
| **OFFLINE** | Required hardware is missing, disabled, incomplete, or has no active Core. Console diagnostics identify the missing requirement. |
| **STANDBY** | Field power allocation is set to 0%. Stored energy is retained; no active protection is provided. |
| **ARMING / RECHARGING** | Hardware is valid and the field is replenishing. |
| **READY** | Field is stable and at full charge. |
| **VENTING** | Heat is being shed; the field is temporarily unavailable. |
| **DOWN / COLLAPSED** | Shield energy was exhausted. Recovery and reboot are required. |
| **REBOOT** | Collapse recovery is in progress. A Gjallarhorn Relay improves recovery. |

## Directional defense and shunting

Shield energy is conserved across six directional banks plus a reserve bank. You can set each directional reinforcement between **0.5× and 2×**. Changing a facing redistributes existing energy; it never creates energy.

To prevent rapid abuse, directional shunting has a **two-second cooldown**. The HUD and Combat LCD mode identify the last pressured facing and current incoming damage pressure.

## Bifrost Transit Signature

**Bifrost Transit Signature** is Aegis' original jump-event sensor. It is informational only: it does not block, steer, drain, identify occupants of, or otherwise alter vanilla Jump Drives.

- The server samples loaded jump-drive grids once per second.
- A displacement of **1 km or more** creates a 15-second trace. A 25 m-radius jumping hull is the 1.0× baseline with a **50 km** receiver range; larger physical grids produce stronger signatures up to **2.5×** and a hard **125 km** range cap.
- Console Status, Combat LCD, and the Shield Health HUD report the trace as **LOCAL**, **DEPARTURE**, or **ARRIVAL**, including jump distance, signature class, effective range, and remaining time.
- Integrations can read the same non-authoritative result through the documented read-only Aegis Framework API. No integration receives jump-drive or shield-energy authority.
- The required Aegis Visual Framework supplies the dedicated transit-pulse presentation material; detection remains in the server-authoritative Aegis runtime.

## Tactical profiles

The following original profiles are designed to specialize, not immunize:

- **Balanced Aegis** — broad, neutral protection.
- **Kinetic Bastion** — stronger against bullets and collisions; weaker against other threats.
- **Energy Veil** — tuned for energy/scripted damage where supported; has tradeoffs elsewhere.
- **Explosive Bulwark** — stronger against missiles and explosions; less efficient against other threats.
- **Collision Ward** — stronger against collision and deformation; weaker against other threats.
- **Utility Screen** — stronger against grinders and drills; weaker against other threats.

With a working Harmonic Modulator, automatic tuning examines recent damage and changes profile at a controlled rate.

## Power, heat, and recovery

- **0%**: standby; no active protection.
- **1–100%**: normal recharge scaling.
- **101–200%**: emergency reinforcement; faster recharge with escalating heat.
- Sustained heat can cause a protective vent.
- Emergency venting deliberately sheds heat and part of the stored energy.

Changing a valid power slider must not turn a charged, valid field falsely offline. If a field reads OFFLINE, the Console hardware diagnostics should be checked first.

## Player Shield Health HUD

The player-local Aegis Shield Health HUD is cosmetic: it reads server-authoritative shield snapshots but never controls the shield or changes another player’s display.

It reports:

- State badge: READY, ARMING, OFFLINE, VENTING, DOWN, or REBOOT.
- Charge ring, percentage, and current/max shield energy.
- Heat, profile, Ship/Station mode, and compatibility framework state.
- All six directional bank values in Full layout.
- Last threatened facing and recent incoming damage pressure.

Use the **Bifrost Console** for **HUD shield status**, **HUD layout**, color, opacity, reduced-flash, sounds, and shield-presentation preferences. These are player-local preferences; no module block duplicates them.

Space Engineers controls the native notification overlay’s exact screen position. Aegis refreshes the HUD persistently for the player’s nearest shielded construct; it does not use unsafe internal UI hooks.

## Shield presentation

Each player can choose a cosmetic presentation from the **Bifrost Console** without changing gameplay:

- Bubble Shield
- Hybrid Bubble
- Hull Impact
- On Contact
- Hidden

Available palettes include Bifrost Cyan, Aegis Gold, Rune Violet, and High Contrast White. Reduced-flash mode and opacity controls are included for accessibility.

## Console and LCD controls

The Bifrost Console exposes full field administration, master field power, framework selection, LCD routing, and player-local HUD/presentation settings. The other Aegis blocks expose only their own system purpose: Capacitor reserve allocation, Flux recharge allocation/venting, Harmonic profile/tuning, and Relay coverage/directional reinforcement.

All Aegis functional blocks retain native Space Engineers controls such as On/Off, Show in Terminal, Show on HUD, name, ownership, and normal toolbar placement.

The Console LCD is always the primary construct readout. Use the Console terminal **Console LCD mode** selector to choose Status, Compact, Combat, or Off; it writes the mode setting automatically. For an additional same-construct LCD, use **Custom Data** to opt into a display mode:

```ini
[TROA Aegis LCD]
Mode=Status
```

An external panel may instead be named `[Aegis LCD]`; it safely defaults to the Status view. Both routes refresh server-side once per second.

Supported values:

| Mode | Output |
| --- | --- |
| `Status` | Complete diagnostics, hardware state, field energy, and banks. |
| `Compact` | Short state, charge, and heat readout. |
| `Combat` | Compact readout plus last hit direction, incoming pressure, and shunt cooldown. |
| `Off` | Clears the Console LCD output. |

## Compatibility and the Aegis Framework

Aegis is built to be useful to server owners, HUD authors, LCD systems, and other authorized mod integrations without turning the shield system into an unreadable black box.

- **Auto** selects the optional WeaponCore monitor when a compatible public contract is available, otherwise it uses Keen-native damage handling.
- **Keen Vanilla** forces native handling only.
- **WeaponCore Bridge** requests the optional monitor. If it is absent, incompatible, or unavailable, Aegis visibly and safely falls back to Keen-native protection.

The private beta also maintains a **versioned, read-only Aegis Framework interface** for approved interoperability. Its purpose is to expose authoritative shield information—construct identity, readiness, lifecycle state, charge, current/max energy, directional-bank status, profile, Ship/Station mode, and framework status—without requiring an integration to scrape terminal text or control the shield itself.

The framework is intentionally one-way for normal integrations: it does **not** permit clients, HUD scripts, LCD tools, or external mods to directly remove, restore, duplicate, or otherwise modify shield energy. Any future control endpoint remains server-validated and subject to the same ownership, faction, and friendly-access checks as normal Aegis controls.

The separate **TROA Aegis Visual Framework** is a required companion used for TROA-owned materials, hex-field presentation, and contact effects. Aegis deliberately remains OFFLINE and provides no protection until the framework is installed, enabled in the same world, and confirms its runtime handshake. At Workshop release, TROAINC will configure it as a Steam Required Item so it is automatically included with Aegis.

## Multiplayer and ownership

- Shield state and damage processing are server-authoritative.
- Player control requests are validated against owner/faction/friendly block access by the server.
- Late joiners receive shield snapshots; stale packets are rejected.
- Connector docking is excluded from construct shielding by default.
- Core failover, splits, merges, reloads, and reconnects are part of private acceptance testing.

## What is not included

TROAINC will not ship copied code, models, sounds, branding, fonts, interfaces, ships, or other protected franchise assets. “Nordic sci-fi” describes original aesthetic direction, not an affiliation with any existing franchise.

This project does not currently publish a Workshop item, binary package, dedicated-server certification, 1.0 tag, or source code.

## Foundation status

The current beta foundation includes the authoritative shield lifecycle, block roles, terminal and toolbar surface, LCD status formats, HUD data path, visual companion handshake, and the read-only interoperability contract described above. These systems are in private acceptance testing. They are not a public source release, public binary release, or Workshop package.

## Documentation

- [Project roadmap](ROADMAP.md)
- [Detailed changelog](CHANGELOG.md)
- [Community and contribution policy](CONTRIBUTING.md)
- [Security and release policy](SECURITY.md)
- [TROAINC Proprietary License — All Rights Reserved](LICENSE.md)

## Rights and permissions

**Copyright © 2026 TROAINC. All rights reserved.** No permission is granted to copy, redistribute, reuse, modify, extract, mirror, or create derivative works from any project material without prior written TROAINC permission. See the [proprietary license](LICENSE.md).

## Official communication

Treat this repository and announcements from TROAINC’s authorized channels as authoritative. Screenshots, extracted files, reuploads, “leaks,” and third-party mirrors are not release announcements.
