# NEP Create Modpack

A Create-focused modpack for the **NEP Gaming** community server, built on top of **Create+ 6.0.0 Alpha f** and extended with Curios, Create addons, airships, relics and quality-of-life mods.

| | |
|---|---|
| Minecraft | 1.21.1 |
| Loader | NeoForge 21.1.256 |
| Base | Create+ 6.0.0 Alpha f (all Create+ mods kept) |
| Server | `create.nepgaming.com.br` |
| Download | [Modrinth](https://modrinth.com/modpack/nep-create-modpack) |

## Installing (players)

1. Install the [Modrinth App](https://modrinth.com/app).
2. Open the [NEP Create Modpack](https://modrinth.com/modpack/nep-create-modpack) page and click **Install**.
3. Give the instance at least **8 GB of RAM** (Instance settings > Java and memory).

**Optional client mods:** Distant Horizons, SSRD, Iris and Colorwheel can be turned off in the Modrinth App if your PC struggles. Shaders are off by default; enable them in the Iris menu.

## Running a server

See [`server/LEIA-ME.txt`](server/LEIA-ME.txt) (Portuguese).

- `server/install-mods.sh` / `install-mods.ps1` download every server-side mod from Modrinth and check its SHA1.
- `server/amp/gerar-pacote-amp.ps1` builds a zip ready to upload to an AMP (CubeCoders) instance.
- `server/mods-servidor.txt` and `server/mods-somente-cliente.txt` list which mods go where.

Ready-made packages are attached to each [release](../../releases).

## Repository layout

```
pack/
  modrinth.index.json   Mod list, versions, hashes and client/server sides
  overrides/config/     Default configs shipped with the pack
server/                 Server install scripts and mod lists
server/amp/             AMP package builder
tools/modlist.py        Regenerates MODLIST.md
CHANGELOG.md            Version history
MODLIST.md              Full mod list with client/server side
```

## Reporting problems

Open an [issue](../../issues/new/choose). For crashes, upload the crash report or `logs/latest.log` to [mclo.gs](https://mclo.gs) and paste the link.

## Releasing a new version

1. Export the `.mrpack` from the Modrinth App.
2. Check that client-only mods (ToadLib, Iris, Colorwheel, MoreCulling, resource packs, etc.) are still marked `server: unsupported`. The Modrinth App can reset these on export.
3. Replace `pack/modrinth.index.json` and `pack/overrides/`, run `python3 tools/modlist.py`, and update `CHANGELOG.md`.
4. Commit, tag (`v1.2.0`), and attach the `.mrpack` and server zips to the GitHub release.

## Credits

All mods belong to their respective authors and are downloaded from Modrinth; this repository contains no mod files. Huge thanks to the Create team and the Create+ pack authors.
