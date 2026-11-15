# Aster Chibi Studio

Android-first browser editor prototype for **VRM 0.x** models.

## Current MVP

- Load a local `.vrm` file in the browser.
- 3D preview with orbit and zoom controls.
- Chibi controls: head, torso, legs, arms, plus 2 / 2.5 / 3 / 4-head presets.
- Big / Adult controls: head, torso, legs, arms, plus Petite / Normal / Tall presets.
- Reset editor values and re-center the model.
- Model processing happens locally in the browser; the model is not uploaded.

## Important limitations

This first commit is a **preview-only deformation prototype**. It adjusts normalized humanoid bone scales for visual testing. This can cause joint, clothing, hair, or skinning distortions on some models.

**VRM export is intentionally disabled.** A normal glTF export is not a valid substitute for a VRM 0.x export and could lose VRM metadata, MToon materials, expressions, spring bones, colliders, and other extension data. A dedicated VRM 0.x-safe export pipeline is a later development milestone.

Compatibility is not guaranteed for every VRM, especially models with unusual humanoid rigs or extensive custom secondary bones.

## Run on GitHub Pages

1. Open repository **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main`, folder `/(root)`, then Save.
4. Open the published Pages URL.

The app loads Three.js and three-vrm from jsDelivr, so an internet connection is required.

## Files

- `index.html` — complete single-page application.

## Planned

- More accurate proportion editing with bone-position compensation.
- Mesh-aware head/body proportion controls.
- Hair, outfit, accessory, and Spring Bone protection.
- Undo / redo and saved presets.
- Verified VRM 0.x export that preserves VRM extensions and metadata.
