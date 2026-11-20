# SAMY

A mixed-use building at Schiestraat 11, Rotterdam (between the Schieblock and the railway north of Rotterdam Centraal), designed for TU Delft's Computational Design Studio (BK7956, minor Spatial Computing).

## The project

The building is mainly housing for three groups: students, elderly and starters (at least 400, 200 and 200 units), combined with at least four other public functions. The brief also asks for daylight in every dwelling, outdoor space, bike and car parking, greenery equal to the plot area, rainwater harvesting, solar power for public spaces, and social control. The design should limit shadow on neighbours, noise and wind, keep the Biergarten intact and keep truck access behind the Schieblock.

The brief can change at any time, so the design is **procedural**: a rule-based model in Houdini that takes the site and the program as inputs and recomputes the design when they change. The model goes from site and context, to a voxel model of the possible building volume, to placing the program and circulation, to evaluating it against the requirements, and finally to an architectural design with plans and façades driven by the same data.

Everything must be reproducible on another computer without changing paths.

## Getting started

1. Run `git lfs install` once, then clone the repo and run `git lfs pull`.
2. Run `uv sync` to create the Python environment (pinned to Houdini's Python 3.13).
3. Download the 3D BAG tiles **9-312-520** and **9-312-524** from https://3dbag.nl/en/download (CityJSON) and put them in `data/context/3dbag/`. They are not in git: anyone can download them.
4. Open `main.hipnc` (Houdini 22.0) from the root of your clone.
5. Before editing `main.hipnc`, run `git lfs lock main.hipnc`, and `git lfs unlock main.hipnc` after pushing.

Keep every path in Houdini relative to `$HIP`, so the scene works on everyone's computer.

## Project structure

| Path | What it holds |
| --- | --- |
| `main.hipnc` | The procedural model: `/obj/SAMY`, with all settings on the `CONTROL` node |
| `data/site/` | Site outlines (CSV for Houdini, DXF for Rhino), in Dutch coordinates (RD New) |
| `data/context/` | Map images (PDOK) and the 3D BAG tiles you download |
| `hda/` | Digital assets, loaded by Houdini automatically |

Map data © Kadaster / PDOK (CC-BY 4.0), buildings from 3D BAG (TU Delft 3D geoinformation).
