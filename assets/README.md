# PNGTuber asset files

The current `manifest.json` lists expected file paths, **but the actual binary PNG/WebP images have not yet been committed**.

The original offline archive (`PNGTuber_Face_Studio_v1.1.zip`, shared in ChatGPT) includes those images. To complete the web build, copy the archive's assets into:

- `poses/` — full neutral base image
- `eyes/` — transparent feathered eye overlays
- `mouths/` — transparent feathered mouth overlays
- `presets/` — full-frame photorealistic expression images

File names must agree with `manifest.json`. You can add and commit these through GitHub's **Add file → Upload files** interface (or `git add assets` from a local clone).

Do not publish private photos to this public repository without considering who can access them.
