# Changelog

## 1.3.0

### Summary

This update greatly expands LoxyCraft’s compressed block system with new families useful for storage, advanced crafting, and late-game progression.

### Fixed

- Fixed the texture of compressed Prismarine blocks
- Fixed compressed Prismarine rendering by using only the first 16x16 frame of the vanilla animated Prismarine texture before applying the compression overlay
- Fixed the visual issue that caused a strange double-color effect on compressed Prismarine

### Added

- Added compressed Nether Star Blocks from x1 to x9
- Added compressed Ender Pearl Blocks from x1 to x9
- Added compressed Blaze Rod Blocks from x1 to x9
- Added compressed Echo Shard Blocks from x1 to x9
- Added compressed Obsidian Blocks from x1 to x9
- Added compressed Amethyst Blocks from x1 to x9
- Added compressed Prismarine Blocks from x1 to x9
- Added compressed Dark Prismarine Blocks from x1 to x9
- Added compressed Blue Ice Blocks from x1 to x9
- Added compressed Bamboo Blocks from x1 to x9
- Added compression recipes for all new block families
- Added reverse decompression recipes for all new block families
- Added loot tables so all new blocks can be recovered correctly
- Added models, blockstates, FR / EN translations, and textures for all new blocks
- Added all new blocks to the LoxyCraft creative tab

### Improved

- Improved premium resource progression by giving Nether Star, Ender Pearl, Blaze Rod, and Echo Shard blocks a full compression chain up to x9
- Improved storage options for useful modpack resources with the new compressed block families
- Improved future advanced crafting support by making compressed blocks a cleaner base for upcoming recipes
- Improved required tool handling depending on block family:
  - diamond or netherite pickaxe for premium blocks such as Nether Star and Obsidian
  - pickaxe for mineral and crystalline blocks
  - axe for compressed Bamboo blocks

### Notes

- Compressed blocks from x1 to x9 use the standard compression logic: 9 blocks of the previous level craft the next level
- Each level can be decompressed back into 9 blocks of the previous level
- No other compressed block families are planned for now in order to avoid unnecessary bloat

## 1.2.0

### Summary

This update adds the Nether Star Infusion system, allowing selected Netherite armor, tools, and weapons to grant one refreshed potion effect while equipped or held.

### Added

- Added Nether Star Infusion
- Added 10 Infusion Cores:
  - Night Vision Infusion Core
  - Water Breathing Infusion Core
  - Resistance Infusion Core
  - Fire Resistance Infusion Core
  - Speed Infusion Core
  - Slow Falling Infusion Core
  - Jump Boost Infusion Core
  - Strength Infusion Core
  - Haste Infusion Core
  - Luck Infusion Core
- Added shapeless recipes for all Infusion Cores using Nether Star Block Core and a matching catalyst item
- Added anvil infusion support for Netherite equipment
- Added refreshed potion effects while infused armor is equipped
- Added refreshed potion effects while infused tools or weapons are held in the main hand
- Added dedicated textures, item models, and translations for all Infusion Cores
- Added tooltips for infused items

### Changed

- Changed Nether Star Block Core so it is now used as the base component for creating Infusion Cores
- Changed tool and weapon infusion behavior so effects only activate from the main hand
- Changed infusion scope so it is limited to Netherite armor, tools, and weapons

### Improved

- Improved Nether Star Block Core usefulness with a new late-game upgrade path
- Improved progression around Nether Star crafting and advanced equipment upgrades
- Improved visual clarity for Infusion Cores with distinct colors and symbols

### Notes

- Each item can only have one infusion effect
- Already infused items cannot be infused again
- Infused armor effects are active only while equipped
- Infused tool and weapon effects are active only while held in the main hand
- Potion effect icons remain visible, but particles are hidden
- On Arkensia, Master Ball crafting requires `cobblemon:master_ball` to be removed from Item Obliterator’s `only_disable_recipes` list

## 1.1.0

### Summary

This update expands LoxyCraft with new compressed blocks, additional natural rock support, advanced crafting recipes, and a complete Nether Star progression chain.

### Fixed

- Fixed the Master Ball recipe layout to match the intended pattern
- Fixed missing creative tab entries for newly added compressed blocks
- Fixed missing or incomplete translations for new compressed blocks
- Fixed tool tags and loot tables for newly added compressed rock blocks

### Added

- Added compressed Bone Blocks from x1 to x9
- Added compressed Soul Sand Blocks from x1 to x9
- Added compressed Soul Soil Blocks from x1 to x9
- Added compressed Deepslate Blocks from x1 to x9
- Added compressed Cobbled Deepslate Blocks from x1 to x9
- Added compressed Tuff Blocks from x1 to x9
- Added compressed Calcite Blocks from x1 to x9
- Added compressed Dripstone Blocks from x1 to x9
- Added compressed Netherrack Blocks from x1 to x9
- Added compressed Basalt Blocks from x1 to x9
- Added compressed Blackstone Blocks from x1 to x9
- Added compressed End Stone Blocks from x1 to x9
- Added compression and decompression recipes for all new compressed blocks
- Added textures, models, blockstates, loot tables, tool tags, and translations for the new compressed blocks
- Added a craft for Echo Shards
- Added a craft for Wither Skeleton Skulls
- Added a craft for Nether Stars
- Added a conditional Cobblemon craft for Master Balls

### Changed

- Changed LoxyCraft’s compressed block system to cover more natural Overworld, Nether, and End rocks
- Changed Master Ball crafting so it now uses Nether Star Block Core as a premium component
- Changed Nether Star crafting so it now has a dedicated progression chain using Echo Shards, Wither Skeleton Skulls, Blaze Rods, and Netherite

### Improved

- Improved the usefulness of Nether Star Block Core as an advanced crafting component
- Improved storage support for natural rock blocks through additional compressed variants
- Improved consistency between compressed block families, recipes, loot tables, and mining behavior
- Improved French naming consistency:
  - Cobblestone compressed blocks use `Pierre`
  - Stone compressed blocks use `Roche`

### Notes

- The Master Ball recipe only loads when Cobblemon is installed
- Nether Star Infusion is planned for a future 1.2.0 update

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
