# SAMY

SAMY is our Houdini project for TU Delft’s Computational Design Studio (BK7956). We’re building a tool that turns editable site footprints into voxel massing studies.

<!-- samy-structure -->
## Getting started

1. Run `git lfs install` once, then clone the repo and run `git lfs pull`.
2. Run `uv sync` to create the Python environment (pinned to Houdini's Python 3.13).
3. Download the 3D BAG tiles **9-312-520** and **9-312-524** from https://3dbag.nl/en/download (CityJSON)
   and put them in `data/context/3dbag/`. They are not in git: anyone can download them.
4. Open `main.hipnc` from the root of your clone.
5. Before editing `main.hipnc`, run `git lfs lock main.hipnc`, and `git lfs unlock main.hipnc` after pushing.

Keep every path in Houdini relative to `$HIP`, so the scene works on everyone's computer.

## Project structure

| Path | What it holds |
| --- | --- |
| `main.hipnc` | The model: `/obj/SAMY` with `CONTROL` and the stages |
| `data/site/` | Site outlines (CSV for Houdini, DXF for Rhino), in RD New |
| `data/context/` | Map images (PDOK) and the 3D BAG tiles you download |
| `hda/` | Digital assets, loaded by Houdini automatically |
