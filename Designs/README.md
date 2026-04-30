# IRON REBELLION Designs

This folder contains distilled production notes made from `Old_Designs`.
Keep `Old_Designs` as the local raw archive, and use this folder as the cleaner handoff packet for Unreal Engine asset work.

## Contents

- `IRON_WALL_UE_MODEL_BRIEF.md` - first playable character model brief.
- `UE_CHARACTER_ASSET_REGISTER.md` - catalog of available GLB prototypes, design sheets, weapons, and priorities.
- `CHARACTER_PART_DETAIL_PROMPTS.md` - prompts/checklists for generating close-up part sheets.

## Current Direction

The first production target is `IRON WALL`, because the current UE slice already uses that role: move the heavy frame, press an objective, and push the frontline gauge.

Use the existing GLB files as blockout/proportion references. For a real UE character, final delivery should become a skeletal mesh or modular skeletal/static mesh set exported from Blender/Maya as FBX, with sockets, material slots, collision, and LODs prepared for UE.

## Suggested UE Content Layout

```text
Content/IRON_REBELLION/Characters/IRON_WALL/
  BP_IRON_WALL_Player
  SK_IRON_WALL
  SK_IRON_WALL_Shield
  SK_IRON_WALL_ShockPile
  MI_IRON_WALL_Armor
  MI_IRON_WALL_Emitters
  ABP_IRON_WALL
```

The reference and prototype source files are organized under the repository-level `Assets` folder.
