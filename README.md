# IRON REBELLION UE

Unreal Engine 5.7 prototype for rebuilding the IRON REBELLION WebGL reference as a higher-fidelity third-person mech combat game.

## Local Setup

- Engine: UE 5.7.2
- Project file: `IronRebellionUE.uproject`
- Current base: Third Person Blueprint template

## Reference Inputs

The WebGL reference was staged locally under:

`D:\Codex\iron-rebellion-main`

Key migrated reference assets are staged in `SourceAssets`:

- `SourceAssets/Mechs`: GLB mech blockouts and 3D manifest
- `SourceAssets/Data`: MVP mech, weapon, and ability JSON
- `SourceAssets/ReferenceBoards`: visual direction boards

## First Milestone

1. Heavy third-person mech movement with shoulder camera.
2. Boost energy and jump/assault movement.
3. Primary projectile weapon with hit feedback.
4. One Linebreak objective and frontline gauge.
5. Simple offline bots moving toward objectives.

## Notes

This project is Blueprint-first because the local machine currently has UE 5.7.2 but no visible Visual Studio/MSVC toolchain. Install Visual Studio Build Tools before adding C++ gameplay modules.
