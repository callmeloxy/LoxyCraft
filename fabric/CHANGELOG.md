# Changelog

## 1.0.0

### Summary

This update expands LoxyCraft with a full compressed block system, new utility blocks, a custom component item, and several vanilla quality-of-life recipes.

### Fixed

- Fixed compressed Grass block rendering by replacing the cube-all model with a proper top, bottom, and side model
- Fixed Glass compressed block transparency
- Fixed Glowstone compressed block lighting
- Fixed missing drops by using the correct Minecraft 1.21.1 loot table path
- Fixed creative tab entries for the new compressed rock blocks
- Fixed French naming:
  - Cobblestone compressed blocks now use `Pierre`
  - Stone compressed blocks now use `Roche`
  - Andesite compressed blocks now use `Andésite`

### Added

- Added the LoxyCraft creative tab
- Added Nether Star Block
- Added Ender Pearl Block
- Added Blaze Rod Block
- Added Echo Shard Block
- Added Nether Star Block Core
- Added compressed blocks from x1 to x9 for:
  - Iron
  - Coal
  - Copper
  - Gold
  - Diamond
  - Emerald
  - Quartz
  - Netherite
  - Lapis
  - Redstone
  - Glowstone
  - Dirt
  - Sand
  - Gravel
  - Grass
  - Glass
  - Stone
  - Cobblestone
  - Clay
  - Granite
  - Diorite
  - Andesite
- Added compression recipes for all compressed blocks
- Added decompression recipes for all compressed blocks
- Added loot tables for all custom blocks
- Added English and French translations
- Added proper tool tags for compressed blocks
- Added conditional Cobblemon recipes that only load when Cobblemon is installed

### Changed

- Changed the project identity from CraftBlock to LoxyCraft
- Changed the mod namespace to `loxycraft`
- Changed the Java package to `com.loxy.loxycraft`
- Changed recipes to the Minecraft 1.21.1 format using `data/<namespace>/recipe/` and `result.id`
- Changed loot tables to the Minecraft 1.21.1 path `data/<namespace>/loot_table/blocks/`
- Changed tool tags to the Minecraft 1.21.1 path `data/minecraft/tags/block/`

### Improved

- Improved compressed block textures by baking layered overlays directly into PNG textures for Fabric compatibility
- Improved Grass compressed blocks with separate top, side, and bottom textures
- Improved Glass compressed blocks with transparent rendering
- Improved Glowstone compressed blocks with light emission
- Improved mining behavior:
  - Dirt, Grass, Gravel, Sand, and Clay can be mined by hand and are faster with a shovel
  - Coal requires a pickaxe
  - Iron, Lapis, Copper, Stone, Cobblestone, Quartz, Granite, Diorite, and Andesite require at least a stone pickaxe
  - Gold, Redstone, Diamond, and Emerald require at least an iron pickaxe
  - Netherite requires at least a diamond pickaxe
- Improved durability balance by using `strength(1.5f)` for compressed blocks

### Notes

- This version focuses on establishing the personal LoxyCraft base
- LoxyCraft is currently kept as a personal utility mod
- The mod now provides a strong foundation for future custom components and quality-of-life additions
