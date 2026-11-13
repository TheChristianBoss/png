# PNGTuber Face Studio

A browser-based editor for building consistent PNGTuber expressions and poses from photographic artwork.

## Features (v1.1)

- **Natural Photo mode:** switch between matching complete expression photos without distorting facial features.
- **Experimental Layer Mixer:** combine mapped eye/mouth regions on a pose with adjustable alignment.
- Switch open/closed mouths to preview speech.
- Import poses and new facial assets, save/load projects, and export transparent 1024 × 1536 PNGs or ZIP packs.

> **Important:** Natural Photo mode is the recommended mode. Experimental facial mixing is not guaranteed to blend cleanly when pose, head angle, or lighting differ. The original bundled photographic images are project artwork, not a generic asset library; they have not yet been uploaded to this public repo.

## Run

Open `index.html` in a browser after cloning/downloading the repository, or use the GitHub Pages site once Pages is enabled. **The GitHub version currently contains code and a manifest, not the bundled photographic assets.** Use the **Import complete expression PNGs** button to load your own transparent 1024 × 1536 PNGs into Natural Photo mode. These stay local to your browser. The previously distributed standalone v1.1 ZIP from ChatGPT contains the complete starter library.

The editor is a static web app, with no backend and no dependencies on external services. Imported files are processed locally in your browser.

## Project layout

- `index.html` — editor UI and application code
- `assets/poses/` — base pose artwork
- `assets/eyes/` — eye-region cutouts
- `assets/mouths/` — mouth-region cutouts
- `assets/presets/` — intact photographic expression presets
- `docs/` — calibration, asset, and deployment guidance
- `.github/workflows/` — GitHub Pages deployment automation

## Standard asset specification

- Canvas: **1024 × 1536**
- File type: transparent PNG for exported character sprites
- Expression pairs: identical body placement and pose, differing only by the speaking face area
- Reference: maintain the approved photorealistic character, including the silver cross and blue wristband
- Calibration landmarks: left eye, right eye, mouth center

See [Asset and alignment guide](docs/ASSETS.md) for guidance.

## GitHub Pages

The repository includes a Pages deployment workflow. In **Settings → Pages**, select **GitHub Actions** as the source if the site isn't already enabled. Workflow status is visible in **Actions**. The live site has **not** been verified as deployed yet.

This project does not include a license declaration; usage/reuse rights are reserved unless the repository owner chooses a license.
