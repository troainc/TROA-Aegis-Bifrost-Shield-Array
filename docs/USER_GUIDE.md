# Aegis Bifrost Shield Array — player and server guide

The project is distributed as two cooperating Space Engineers mods: the server-authoritative **Aegis Bifrost Shield Array** and the client presentation **Aegis Visual Framework**. The framework renders the HUD/effects; the gameplay mod owns shield state, power, damage handling, and server decisions. The public GitHub repository is documentation-only. Use the Workshop descriptions for the actual released files, exact dependencies, and supported game version.

## Install and verify

Subscribe to both matching Workshop items and add both to the world/server mod list. Check the Workshop instructions for installation order and compatibility. Restart the game and dedicated server after changing either component. On startup, confirm the shield Core/Console is present and that its status indicates the field is operating. A visible HUD by itself is not proof that the server-side protection is online.

## Core and Console setup

Place the required shield hardware on a supported construct and supply its configured power demand. Use the Core/Console terminal settings for shield enable/disable, power allocation, field/player policy, service options, and player HUD size where those controls are included in the released version. The player-facing HUD indicates operating state and directional shield telemetry; when protection is off or unavailable it should display an offline state rather than imply full protection. Settings that affect gameplay are synchronized by the server; personal display preferences can be client-local.

Friendly construct owners can use tools on their own ship/base while inside their own field. The visible shield boundary uses the configured field/bubble clearance; clients can receive entering/exiting notices and sound cues when crossing their boundary. Confirm that notices and HUD status match the server state after relogging and changing grids.

## Power, damage, and compatibility

Power allocation affects shield behavior according to the release's stated scaling and increases Core demand. If the grid cannot supply that demand, the Core may go offline and armor can take damage. Inspect the Core status and power supply before increasing allocation. Damage handling is server-authoritative; WeaponCore detection/observation does not necessarily provide a universal projectile cancellation hook. Do not treat WeaponCore detection, a full HUD percentage, or a visual field as proof that every weapon class is blocked. Test each weapon path against a disposable grid on the exact dedicated-server build.

## Acceptance and recovery

Use controlled tests for enable/disable, power loss, each shield face, breach/collapse, friendly tools, bubble entry/exit, reconnect, and both Keen and WeaponCore weapon paths. Keep server logs and matching mod versions. The project is an Alpha candidate and current live acceptance/known limits are described in the root README. If armor takes damage while the HUD appears full, stop combat testing, capture the logs and weapon type, and report the exact server/client/mod versions to TROA.
