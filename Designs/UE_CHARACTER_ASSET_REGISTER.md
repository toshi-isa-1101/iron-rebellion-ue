# UE Character Asset Register

This register maps the old design archive into the new UE asset pipeline.

## Organized Source Assets

```text
Assets/PrototypeModels/
  hmr_iron_wall.glb
  hmr_siege_breaker.glb
  lmr_scout_eye.glb
  lmr_sprinter.glb
  lmr_wraith.glb
  mmr_lancer.glb

Assets/Reference/CharacterSheets/
  hmr_iron_wall_three_view_weapon_sheet.png
  hmr_siege_breaker_three_view_weapon_sheet.png
  lmr_scout_eye_three_view_weapon_sheet.png
  lmr_sprinter_three_view_weapon_sheet.png
  lmr_wraith_three_view_weapon_sheet.png
  mmr_lancer_three_view_weapon_sheet.png

Assets/Reference/Boards/
  ir_hmr_design_board.png
  ir_lmr_design_board.png
  ir_mmr_design_board.png
  mech_invaders_regular_enemy_board.png
  colossus_boss_board_01.png
  colossus_boss_board_02.png
```

## Player Frame Priority

| Priority | ID | Class | Gameplay Role | Prototype GLB | Model Sheet |
| --- | --- | --- | --- | --- | --- |
| 1 | `hmr_iron_wall` | HMR | shield wall / objective push | `Assets/PrototypeModels/hmr_iron_wall.glb` | `Assets/Reference/CharacterSheets/hmr_iron_wall_three_view_weapon_sheet.png` |
| 2 | `mmr_lancer` | MMR | precision DPS / counter fire | `Assets/PrototypeModels/mmr_lancer.glb` | `Assets/Reference/CharacterSheets/mmr_lancer_three_view_weapon_sheet.png` |
| 3 | `lmr_wraith` | LMR | stealth scout / disruption | `Assets/PrototypeModels/lmr_wraith.glb` | `Assets/Reference/CharacterSheets/lmr_wraith_three_view_weapon_sheet.png` |
| 4 | `lmr_sprinter` | LMR | flanker / boost harassment | `Assets/PrototypeModels/lmr_sprinter.glb` | `Assets/Reference/CharacterSheets/lmr_sprinter_three_view_weapon_sheet.png` |
| 5 | `lmr_scout_eye` | LMR | scan / marking support | `Assets/PrototypeModels/lmr_scout_eye.glb` | `Assets/Reference/CharacterSheets/lmr_scout_eye_three_view_weapon_sheet.png` |
| 6 | `hmr_siege_breaker` | HMR | artillery / structure breaker | `Assets/PrototypeModels/hmr_siege_breaker.glb` | `Assets/Reference/CharacterSheets/hmr_siege_breaker_three_view_weapon_sheet.png` |

## Weapon/Module Notes

| Frame | Primary Module | Secondary Module | UE Notes |
| --- | --- | --- | --- |
| IRON WALL | Heavy Shield | Shock Pile | shield should have collision and barrier sockets |
| SIEGE BREAKER | Heavy Railgun | Missile Pod | rail cannon and stabilizers should be separate animated modules |
| LANCER | Rail Lance | Counter-Fire Shield | rifle barrel needs clear muzzle/charge socket |
| WRAITH | Pulse Rifle | Emergency Knife | EW membrane material should support transparency/emissive scan lines |
| SPRINTER | Burst SMG | Dash Blade | calf boosters need sockets and emissive heat material |
| SCOUT-EYE | Marker Carbine | Recon Drone | chest eye should be separate emissive mesh/material |

## Import Guidance

- Treat GLBs as blockout/proportion references, not final production rigs.
- Final UE import should use FBX skeletal mesh or modular FBX assets from DCC cleanup.
- Preserve readable silhouettes at LOD2.
- Keep material slots separate for armor, red panels, dark frame, cyan sensors, and amber emitters.
- Avoid baking shield/pile gameplay parts into one inseparable mesh if they need collision or VFX.

## Next Asset Tasks

1. Create cleaned `SK_IRON_WALL` from the prototype GLB and design sheet.
2. Add sockets listed in `IRON_WALL_UE_MODEL_BRIEF.md`.
3. Create first material instances and emissive masks.
4. Replace mannequin mesh in `BP_IRON_WALL_Player`.
5. Add shield collision/VFX component to the player Blueprint.
