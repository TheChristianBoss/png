# Asset and facial mapping guide

## Status
The GitHub repository currently contains the editor source and an asset *manifest*, but the referenced PNG/WebP files have **not yet been uploaded**. The original offline v1.1 ZIP in ChatGPT includes the bundled assets and runs as-is. The repository version needs the files described in `assets/manifest.json` before its 37 built-in photo presets will display.

## Canvas and reference
- Export at **1024 × 1536 RGBA PNG**. Do not bake a black, gradient, or checkerboard background into the output.
- Keep the same character, same necklace/cross, blue bracelet, hairstyle, waist crop and face position.
- Natural Photo is the safe/default mode: each expression uses a complete photographic PNG or WebP.
- Each open/closed expression pair should be derived from the *same body image* with minimal edits, not independently regenerated bodies.

## Mapping body and feature parts
For each pose, record three anchors in absolute 1024 × 1536 canvas pixels:
1. `l`: center of left eye
2. `r`: center of right eye
3. `m`: center of mouth

When a face feature is extracted from a source image, store its source landmarks, crop origin, and feathered alpha mask. Compute scaling/rotation from the eye line of the source and target, then translate the source mouth center to the target mouth center. Do not stretch a large eye patch without preserving the underlying facial proportions; misalignment produces the distorted results from v1.0.

## Import
- `assets/presets/preset_001.webp`, etc.: natural expression photographs; full-sized.
- `assets/poses/pose_base.png`: full-size neutral base pose.
- `assets/eyes/`, `assets/mouths/`: only the transparently feathered regions for experimental mixing.
- Check `assets/manifest.json` for all expected paths.

## Privacy and file size
This is a public repository. Do not commit personal images unless you intentionally want them publicly downloadable. A transparent 1024 × 1536 PNG may be several MB. WebP can reduce the storage size, but verify alpha transparency after converting.

## Acceptance tests
- All references in `assets/manifest.json` resolve to actual files.
- Background alpha must be transparent (not an opaque checkerboard).
- Image dimensions must be 1024 × 1536.
- Open/closed pairs must not shift the body.
- The original face and wristband details must match the reference.
