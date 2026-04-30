# IRON REBELLION Source Assets

This repository-level `Assets` folder stores modeling references and prototype source files. These are not runtime UE `Content` assets yet.

## Folder Map

```text
Assets/PrototypeModels/       GLB blockouts copied from Old_Designs
Assets/Reference/CharacterSheets/ three-view and weapon sheets
Assets/Reference/Boards/      broader visual boards
```

## Usage

- Use GLBs for blockout, scale, silhouette, and quick UE import tests.
- Use PNG sheets as modeling reference for Blender/Maya cleanup.
- Final runtime assets should be imported into `Content/IRON_REBELLION/...`.
- Binary source assets are tracked through Git LFS.

## First Target

`IRON WALL` is the first production target because the current playable UE slice already supports movement, boost, objective pressure, frontline GameState, and HUD.
