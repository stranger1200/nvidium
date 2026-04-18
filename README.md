# Nvidium

[![Modrinth](https://img.shields.io/modrinth/dt/nvidium?logo=modrinth)](https://modrinth.com/mod/nvidium)

Nvidium is an alternate rendering backing for sodium, it uses cutting edge nvidia features to render huge amounts of
terrain geometry at very playable framerates.

### Requires sodium and an nvidia gtx 1600 series or newer to run (turing+ architecture)

---

## 1.20.1 Sodium 0.5.10+ Compatibility Patch

This fork patches Nvidium 0.2.6-beta to work with Sodium 0.5.10 and above on Minecraft 1.20.1, primarily to support the [unofficial Voxy 1.20.1 backport](https://github.com/mcrcortex/voxy) which requires Sodium >=0.5.10.

### What changed
- Broadened Sodium version constraint from `=0.5.7 | =0.5.8` to `>=0.5.7` in `fabric.mod.json`
- Updated `NvidiumCompactChunkVertex.getEncoder()` to use the new `ChunkVertexEncoder.write(long, Material, Vertex[], int)` signature introduced in Sodium 0.5.10, which changed from writing a single vertex per call to writing a full quad (4 vertices) per call

### Tested with
- Minecraft 1.20.1
- Fabric Loader 0.19.2
- Sodium 0.5.13+mc1.20.1 *(other versions >=0.5.10 may work but are untested)*
- Voxy 0.1.6-alpha (unofficial 1.20.1 backport)