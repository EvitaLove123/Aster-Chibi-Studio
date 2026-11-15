# Aster Chibi Studio

An Android-first, browser-based proportion editor prototype for **VRM 0.x**.

## Current features

- Load a local `.vrm` file from your phone.
- 3D preview with touch orbit and pinch-to-zoom.
- Switch between **Chibi** and **Adult** modes at any time.
- Adjustable head scale and humanoid segment proportions.
- Chibi presets: 2-head, 2.5-head, 3-head and 4-head.
- Adult presets: Petite, Normal, Tall and Reset.
- Reset proportions and re-center the model.
- English interface.
- All model processing happens locally in the browser. The model is not uploaded.

## Proportion editing: current implementation

The editor now changes normalized humanoid joint offsets for the torso, arms and legs. The skinned body follows these joint-position changes, so this is more than a simple whole-avatar scale.

The head control currently scales the normalized head bone. Separate hair, ears, tails and accessories are not directly edited, but any item skinned to or parented under an edited bone may still move or deform. Rigs vary, so inspect the result carefully with each model. This prototype does **not** yet guarantee perfect accessory preservation or studio-quality mesh fitting.

## VRM export status

**VRM export is disabled.** A generic glTF export is not a valid substitute for VRM 0.x export and may lose VRM metadata, MToon materials, expressions, Spring Bones, colliders and other extension data. A dedicated VRM 0.x-safe export pipeline is still required.

## Run on GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/(root)`.
4. Save, then open the published Pages URL.

The app loads Three.js and three-vrm from jsDelivr, so an internet connection is required.

## Mobile notes

Large VRM files can use substantial memory. The current file-size guard rejects files above 250 MB, but smaller files may still exceed the available memory of some Android devices.

## Roadmap

- Better mesh-aware head and body fitting.
- Robust preservation of separate and skinned hair, ears, tails, outfits and accessories.
- Rig-aware joint adjustment and deformation safeguards.
- Undo / redo and user presets.
- Verified VRM 0.x export that preserves original VRM extensions and metadata.
