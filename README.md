# CraftWater-patches

Patch pack for **CraftWater**, a performance fork of CraftBukkit 1.2.5.
This repository contains only diff data (`.cw` modules) — no Mojang/Bukkit
sources and no compiled server jars.

The corresponding builder/patcher lives in:
**https://github.com/99965bs/CraftWater**

## Layout

```
pack.yml                     # index: base info + list of releases
releases/
  R1.0/
    manifest.yml             # modules of this release (id, cw, category, deps)
    *.cw                     # one zip per module (patch.yml + patch.diff + files/)
  ...
  R4.0/
```

Each `.cw` is a zip containing `patch.yml`, `patch.diff` and (optionally) a
`files/` folder with new files. The patcher downloads a release manifest and the
`*.cw` modules listed in it, then applies them on top of the CraftBukkit base.

## Base

The base archive is **not** stored here. `pack.yml` only records its name,
download URL and SHA-256; the patcher downloads and verifies it locally:

- `CraftBukkit 1.2.5-R5.0`
- SHA-256 `3db139dbfec28742da3c70b07bbb93d48d277d0791f0cfa31f8fba8d6bc422f1`

## License

This patch pack is a derivative work of CraftBukkit and is distributed under the
**GNU General Public License v3.0** (see `LICENSE`). CraftBukkit/Minecraft code
is copyright Mojang AB. The CraftWater builder in the `CraftWater` repository is
licensed separately under MIT.
