# Public Project Context

TROA Aegis Bifrost Shield Array is a proprietary TROAINC Space Engineers shield project in private reliable-beta acceptance testing.

The public repository is an information hub only. The active runtime, Aegis Visual Framework, client HUD, models, textures, sounds, tests, and packages remain private in Foundry.

TROA Aegis Visual Framework is a required packaged runtime companion. It provides the TROA visual contract and must be enabled through the eventual Workshop Required Items chain, but visual readiness is not an authority gate: a delayed handshake cannot prevent valid server-side protection. Before an authorized Workshop release, TROAINC must publish the framework and configure it as an Aegis Steam Required Item.
- 2026-09-24: Bifrost Transit Signature is in private-beta acceptance testing. It is a bounded, server-authoritative read-only sensor for nearby vanilla jump-drive displacement; it supplies temporary Local, Departure, or Arrival telemetry only and cannot alter a jump.
- 2026-09-24: The required Visual Framework now owns Transit Signature presentation material only. Detection, jump behavior, shield energy, and permissions remain outside the framework in private Aegis runtime code.
- 2026-09-24: Transit Signature is physically size-scaled: 25 m radius establishes 1.0× / 50 km; larger jump grids scale up to 2.5× / 125 km, with proportional visual wake and no additional gameplay authority.
- 2026-09-24: Bifrost Wake Dust is a bounded, client-side cyan/violet presentation layer at Transit Signature departure and arrival endpoints. It uses the required Visual Framework material, scales with the signal class, respects Hidden/reduced-flash preferences, and has no authority over jumps or shields.
- 2026-09-24: Bifrost Jump Wave is the companion bounded endpoint surge: departure contracts violet-to-cyan and arrival expands cyan-to-violet. It shares the visual-material route, respects accessibility settings, and cannot alter a vanilla jump.
- 2026-09-24: The private-beta exact-position Shield Health HUD renderer now belongs to the required Visual Framework boundary. It draws player-local telemetry at the top-right from a versioned, read-only snapshot; shield authority remains exclusively in the server runtime.
- 2026-09-23: Private beta repaired authoritative block-damage interception and added a synchronized module On/Off control plus toolbar toggle on every functional Aegis block. Public documentation only; no implementation or release artifact is present here.
- 2026-09-13: Every Aegis block supports direct visible-surface player terminal access, retaining native functional-block controls and its own role-specific Aegis controls. The public repository remains documentation-only.
- 2026-09-10: LCD status output supports documented Custom Data routing and a resilient [Aegis LCD] external panel-name tag; runtime source remains private in Foundry.

- 2026-09-10: Aegis Suit Induction is a private-beta, server-authoritative friendly suit-recharge feature; it has bounded real-field range, terminal-access authorization, and a shield-energy cost.

- 2026-09-10: Suit Induction is implemented through the supported server-side Visual Script player-energy API; direct internal character/battery access is intentionally prohibited.

- 2026-09-10: Bifrost Console exposes a terminal LCD Mode selector with distinct Status, Compact, Combat, and Off output; external parsing tolerates normal Custom Data formatting variations.

- 2026-09-13: Aegis Life-Support Seal is implemented privately for both ships and stations. Ships are constrained to live construct bounds plus 10 m; stations require Core + Capacitor Rune + Flux Weave and use their bounded station envelope. It provides O2, narrow ambient thermal protection, and authorized Suit Induction only while the field is active.

- 2026-09-13: Aegis controls are role-specific. Bifrost Console owns player-local presentation preferences; Capacitor owns reserve allocation; Flux owns recharge/venting; Harmonic owns profile/tuning; Relay owns coverage/facings. Native Space Engineers functional-block controls remain on every block.
