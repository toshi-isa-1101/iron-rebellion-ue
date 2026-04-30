# IRON WALL UE Model Brief

## Goal

Turn the existing IRON WALL design into a UE-ready playable heavy frame.

The model must read immediately as a defensive wall unit: broad rectangular torso, oversized shield, compact heavy legs, right-arm shock pile, amber barrier emitters, worn off-white armor, red shield panels, and dark gunmetal internal mechanisms.

## Source References

- Design sheet: `Assets/Reference/CharacterSheets/hmr_iron_wall_three_view_weapon_sheet.png`
- Prototype GLB: `Assets/PrototypeModels/hmr_iron_wall.glb`
- Original source archive: `Old_Designs/charactor/hmr_iron_wall/`

## Gameplay Read

- Role: line control, shield wall, enemy pushback, objective pressure.
- Main silhouette: wide shoulders, flat shield face, short powerful stance.
- Important readability from TPS camera: shield state, amber barrier edge, right-arm pile tip, heavy feet, cyan head/chest sensors.
- Current UE slice usage: player pawn, boost movement, objective push, frontline HUD.

## Model Package

Recommended final delivery:

```text
SK_IRON_WALL.fbx
SK_IRON_WALL_Shield.fbx
SK_IRON_WALL_ShockPile.fbx
T_IRON_WALL_Armor_BaseColor.png
T_IRON_WALL_Armor_Normal.png
T_IRON_WALL_Armor_ORM.png
T_IRON_WALL_EmissiveMask.png
```

`hmr_iron_wall.glb` can be imported as a temporary blockout/proportion reference, but final gameplay should use cleaned skeletal mesh assets.

## Scale And Orientation

- Unreal units: centimeters.
- Forward axis in UE: X forward.
- Up axis in UE: Z up.
- Target height: 240-280 cm, clearly taller and wider than the mannequin.
- Shoulder width: roughly 1.5x to 1.8x a standard humanoid frame.
- Shield height: from upper chest to below knee.
- Shield width: enough to cover most of the torso from front view.

## Body Modules

### Core Chassis

- Box-heavy torso with layered front plates.
- Small head sunk into shoulder armor, with cyan optical slit or small sensor cluster.
- Dark internal frame visible between armor plates.
- Chest/abdomen amber service lights, not too bright.

### Shoulders

- Oversized rectangular shoulder blocks.
- Asymmetrical scratches and repair plates.
- Keep the top plane readable from a slightly elevated TPS camera.

### Left Arm And Shield

- Shield should be a separate mesh or at least a separate material/section.
- Flat front face, thick beveled rim, red diagonal panel, chipped paint.
- Back side needs handles, hinge brackets, pistons, and emitter housings.
- The shield should support both passive carried pose and deployed/braced pose.

### Right Arm And Shock Pile

- Forearm-mounted industrial pile driver.
- Conical or drill-like impact tip.
- Cylindrical driver housing with amber heat rings.
- Pile tip must have a clean socket for hit VFX and collision traces.

### Legs And Feet

- Short, heavy, stable.
- Large feet with broad soles.
- Visible ankle hydraulics and knee pistons.
- Avoid thin heroic legs; this frame should feel like construction machinery.

### Backpack And Emitters

- Compact backpack, vents, cable bundles, optional radio/antenna.
- Amber barrier emitter strips along shield rim and torso edge.
- Cyan sensors stay small; amber is the shield/barrier language.

## Sockets

Create these sockets on the skeletal mesh or relevant child meshes:

```text
socket_camera_lock
socket_vfx_core
socket_muzzle_primary
socket_shock_pile_tip
socket_shock_pile_charge
socket_shield_attach
socket_shield_barrier_origin
socket_shield_vfx_top
socket_shield_vfx_bottom
socket_shield_vfx_left
socket_shield_vfx_right
socket_footstep_l
socket_footstep_r
socket_booster_l
socket_booster_r
```

## Collision

- Character movement remains a capsule.
- Shield needs a separate collision mesh or simple box for block/deflect gameplay.
- Shock pile needs a short forward hitbox or trace origin at `socket_shock_pile_tip`.
- Keep visual mesh collision disabled unless needed for traces.

## Materials

Use separate material slots so gameplay VFX can target them:

| Slot | Purpose | Notes |
| --- | --- | --- |
| `M_IR_Armor_White_Worn` | main armor | off-white, chipped, rough metal |
| `M_IR_Red_WornPanels` | red identity panels | shield/front skirt/shoulder marks |
| `M_IR_Dark_Frame` | inner machinery | gunmetal, cables, pistons |
| `M_IR_Amber_Emitter` | barrier lights | emissive, shield rim, vents |
| `M_IR_Cyan_Sensor` | optics | head/chest sensors |
| `M_IR_Rubber_Cable` | hoses/cables | near black, high roughness |

Suggested palette:

```text
armorWhite      #d8d5ca
redMark         #b64032
gunmetal        #15191c
blackJoint      #07090a
cyanGlass       #38c7d8
amberGlow       #e1a743
darkScuff       #2b2d2c
```

## LOD Budget

- LOD0: 45k-60k triangles for close TPS view.
- LOD1: 25k-35k triangles for combat mid-range.
- LOD2: 10k-16k triangles, preserve shield, head, shoulder blocks, pile silhouette.
- Texture target: 2K for prototype, 4K for hero close-up pass.

## Animation Set

Minimum playable set:

```text
Idle_Braced
Walk_Heavy
Jog_Heavy
Boost_Start
Boost_Loop
Boost_End
Shield_Deploy
Shield_Brace_Loop
ShockPile_Windup
ShockPile_Impact
HitReact_Light
HitReact_Heavy
```

Readability notes:

- Boost should feel like a heavy surge, not a nimble dash.
- Shield deploy should expose amber arc VFX clearly.
- Shock pile impact should have short windup, bright tip, and ground impulse.

## Blender/Maya Cleanup Tasks

1. Import `Assets/PrototypeModels/hmr_iron_wall.glb` as a blockout reference.
2. Build clean modular meshes over it.
3. Split shield and shock pile into separate named modules.
4. Set pivots at attachment hinges, not at world origin.
5. Create low-poly collision proxies.
6. Assign material slots according to the table above.
7. Add sockets/bones for VFX and gameplay traces.
8. Export to FBX with centimeter scale and X-forward/Z-up convention.

## UE Import Checklist

- Import as skeletal mesh if animated as one frame.
- Import shield/shock pile as separate skeletal or static child assets if they need independent animation/collision.
- Verify scale against UE mannequin.
- Create material instances using the named slots.
- Add sockets in Skeleton editor if not exported.
- Create Blueprint components for shield collision and pile hit trace.
- Replace temporary mannequin mesh in `BP_IRON_WALL_Player`.

## Open Questions

- Final rig: custom mech skeleton or UE mannequin retarget base?
- Shield gameplay: always attached, deployable, or detachable defensive plate?
- Shock pile: melee trace only, projectile shockwave, or both?
- Should IRON WALL be one hero frame or first member of a modular HMR family?
