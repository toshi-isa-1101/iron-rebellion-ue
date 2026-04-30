# IRON REBELLION UE Migration Plan

## Local References

- Web reference: `D:\Codex\iron-rebellion-main`
- Unreal prototype: `D:\Codex\IronRebellionUE`
- Engine: `D:\UE_5.7` / UE 5.7.2

## Direction

Build a third-person mech combat prototype first, then raise fidelity in focused passes.

1. Preserve the current Linebreak loop: 16v16 offline, 3 lanes, 3 objectives, frontline gauge.
2. Rebuild the player feel in UE: shoulder camera, reticle, lock-on, boost, jump, primary fire.
3. Convert mech/weapon/ability JSON into Unreal DataAssets or DataTables.
4. Import GLB blockout mechs as source assets, then replace with rigged skeletal meshes.
5. Build RIFT-01 as a playable greybox before final art.
6. Add AI roles: LMR flank/scout, MMR fire lane, HMR frontline, COLOSSUS push/breakpoint.

## First Unreal Milestone

- Blueprint-only third-person project opens cleanly.
- One mech pawn moves with heavy acceleration and boost energy.
- One test weapon fires projectiles with hit feedback.
- One objective updates the frontline gauge.
- Bots can move toward objectives and respawn.

## Technical Note

The current machine has UE 5.7.2 and UnrealBuildTool, but no visible Visual Studio/MSVC toolchain.
Start Blueprint-first now; install Visual Studio Build Tools before adding C++ gameplay modules.
