# SAMY

A mixed-use building at Schiestraat 11, Rotterdam (between the Schieblock and the railway north of Rotterdam Centraal), designed for TU Delft's Computational Design Studio (BK7956, minor Spatial Computing).

The building is mainly housing for students, elderly and starters (at least 400, 200 and 200 units), combined with at least four public functions. Because the brief can change at any time, the design is **procedural**: a rule-based Houdini model that takes the site and the program as inputs and recomputes the design when they change.

## Setup

You need Houdini 22.0, [Git LFS](https://git-lfs.com) and [uv](https://docs.astral.sh/uv/).

1. Clone the repo and get the Houdini files:
   ```
   git lfs install
   git clone git@github.com:SimeonVutov/SAMY.git
   cd SAMY
   git lfs pull
   ```
2. Create the Python environment: `uv sync`
3. Open `main.hipnc` in Houdini.

## Working together

`main.hipnc` and the assets in `hda/` can't be merged, so only one person may change a file at a time. Lock it before you edit and unlock it after you push:

```
git lfs locks                 # who is editing what
git lfs lock main.hipnc
git lfs unlock main.hipnc
```

Keep every path in Houdini relative to `$HIP`, so the scene works on everyone's computer.

## Repository

| Path | What it holds |
| --- | --- |
| `main.hipnc` | The model, in `/obj/SAMY`. Settings are on the `CONTROL` node |
| `hda/` | The modules the model is built from |
| `data/site/` | Site outlines, zones and site elements (CSV for Houdini, DXF for Rhino) |
| `data/context/` | Roads, noise maps, map images and the 3D BAG tiles |
| `docs/` | How the model works: start with [docs/network.md](docs/network.md) |

Map data © Kadaster / PDOK (CC-BY 4.0), buildings from 3D BAG (TU Delft 3D geoinformation), noise maps © RIVM.
