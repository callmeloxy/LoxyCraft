# Changelog

## 1.8.0

### Summary

This update adds a set of recycling recipes for wooden components, making it easier to recover planks from crafted blocks made by mistake or in excess.

### Added

- Added recycling recipes for wooden slabs
- Added recycling recipes for wooden stairs
- Added recycling recipes for wooden trapdoors
- Added recycling recipes for wooden doors
- Added recycling recipes for wooden pressure plates
- Added recycling recipes for Bamboo Mosaic slabs

### Improved

- Improved wooden slab recycling:
  - 2 slabs -> 1 plank
- Improved wooden stair recycling:
  - 2 stairs -> 3 planks
- Improved wooden trapdoor recycling:
  - 1 trapdoor -> 3 planks
- Improved wooden door recycling:
  - 1 door -> 2 planks
- Improved wooden pressure plate recycling:
  - 1 pressure plate -> 2 planks
- Improved Bamboo Mosaic slab recycling:
  - 2 Bamboo Mosaic slabs -> 1 Bamboo Mosaic block

### Notes

- Recipes cover the vanilla wood families available in Minecraft 1.21.1:
  - Oak
  - Spruce
  - Birch
  - Jungle
  - Acacia
  - Dark Oak
  - Mangrove
  - Cherry
  - Bamboo
  - Crimson
  - Warped
- Pale Oak is not included because it does not exist in Minecraft 1.21.1
- This update is recipes-only:
  - no Java changes
  - no new config
  - no new item
  - no new block
  - no texture changes
- Stone-based recycling variants are intentionally kept for a future dedicated update

## 1.7.0

### Summary

This update improves the infusion system with support for compatible multi-infusions, configurable Infusion Extractor behavior, and automatically generated configuration comment files.

### Fixed

- Fixed legacy items using the old `loxycraft_infusion` format so they are still recognized correctly
- Fixed new infusions so they now use the internal `loxycraft_infusions` format
- Fixed tooltips so they now display multiple infusions correctly on the same item
- Fixed the Infusion Extractor so it still does not remove the Unbreakable upgrade
- Fixed `CONFIG_COMMENTS_FR.txt` and `CONFIG_COMMENTS_EN.txt` so they are now actually generated in the config folder

### Added

- Added support for compatible multi-infusions on certain equipment
- Added a new internal storage format to handle multiple infusions on the same item
- Added compatibility with older already-infused items
- Added display support for multiple infusions in tooltips
- Added support for keeping a different level for each infusion
- Added the `infusionManagement.extractMode` config option
- Added extraction modes:
  - `ALL`
  - `FIRST`
  - `LAST`
- Added automatically generated config comment files:
  - `config/LoxyCraft/CONFIG_COMMENTS_FR.txt`
  - `config/LoxyCraft/CONFIG_COMMENTS_EN.txt`

### Changed

- Changed the allowed multi-infusion combinations to:
  - Helmet: Night Vision + Water Breathing
  - Chestplate: Resistance + Fire Resistance
  - Boots: Slow Falling + Jump Boost
  - Axe: Haste + Strength
  - Hoe: Haste + Luck
- Changed the following items so they remain limited to a single infusion:
  - Leggings: Speed only
  - Sword: Strength only
  - Pickaxe: Haste only
  - Shovel: Haste only
- Changed `extractMode = ALL` so it removes all effect infusions
- Changed `extractMode = FIRST` so it removes the first infusion according to the mod’s internal order
- Changed `extractMode = LAST` so it removes the last infusion according to the mod’s internal order

### Improved

- Improved some items so they can now receive two compatible infusions
- Improved infusion flexibility so compatible infusions can be applied in any order
- Improved upgrade handling so an existing infusion can still be upgraded with the same Infusion Core
- Improved Unbreakable handling so it remains separate from effect infusions
- Improved the Infusion Extractor so it can now remove all infusions or only part of them depending on the config
- Improved configuration readability with comment files explaining the main `loxycraft.json` options
- Improved config setup so comment files are copied automatically into `config/LoxyCraft/`

### Notes

- Multi-infusion is not unrestricted: only explicitly allowed combinations work
- Incompatible combinations are refused in the anvil
- Each infusion keeps its own level
- The Unbreakable upgrade remains compatible with effect infusions
- The comment files do not replace `loxycraft.json`; they are only reading helpers
- Config changes can be reloaded with:
  - `/loxycraft reload`

## 1.6.0

### Summary

This update adds an equipment recycling system and improves infusion handling with two new tools: the **Infusion Extractor** and the **Equipment Recycling Core**.

### Fixed

- Fixed material recycling so it no longer uses the anvil
- Fixed material recycling so it no longer costs XP
- Fixed the Equipment Recycling Core so it is no longer used for material recycling and is now dedicated to enchantment extraction
- Fixed material recycling so items with normal enchantments are rejected
- Fixed material recycling so items with only curses can still be recycled
- Fixed material recycling so infused items are rejected by default
- Fixed material recycling so Unbreakable items are rejected by default

### Added

- Added the **Infusion Extractor**
- Added the **Equipment Recycling Core**
- Added diamond equipment recycling in the crafting table
- Added Netherite equipment recycling in the crafting table
- Added a material return system based on the remaining durability of the item
- Added infusion extraction through the anvil
- Added enchantment extraction through the anvil
- Added new config options for recycling and infusion management
- Added `/loxycraft reload` support for the new config options

### Improved

- Improved equipment recycling so it now happens directly in the crafting table, without XP and without any extra item
- Improved diamond equipment recycling so it now returns diamonds based on item condition
- Improved Netherite equipment recycling so it now returns Netherite Scraps based on item condition
- Improved recycling output clarity with defined return tiers:
  - 100% durability: maximum return
  - 99% to 75%: one step lower
  - 74% to 50%: two steps lower
  - 49% to 25%: three steps lower
  - 24% to 1%: four steps lower
  - 0%: no return
- Improved infusion management by allowing the Infusion Extractor to remove an effect infusion without destroying the item
- Improved Unbreakable handling so the Infusion Extractor does not remove the Unbreakable upgrade
- Improved enchantment recovery by allowing the Equipment Recycling Core to extract normal enchantments from an item
- Improved enchantment output so extracted enchantments are returned as an enchanted book
- Improved curse handling so curses stay on the original item during enchantment extraction
- Improved overflow handling so the extracted enchanted book drops on the ground if the inventory is full

### Notes

- Equipment recycling only works for diamond and Netherite armor, tools, and weapons
- Iron and gold equipment are intentionally excluded because Minecraft already supports their recycling through smelting
- Crafting-table recycling does not require any XP
- Infusion extraction remains an anvil action with a configurable cost
- Enchantment extraction remains an anvil action with a configurable cost
- The system is configurable in:
  - `config/LoxyCraft/loxycraft.json`
- The new options can be reloaded with:
  - `/loxycraft reload`

## 1.5.0

### Summary

This update improves LoxyCraft’s infusion system with configurable infusion levels, a dedicated server configuration, and a reload command to adjust settings without restarting.

### Fixed

- Fixed the client tooltip so infusion levels now display correctly
- Fixed config behavior to prevent infusion levels above V
- Fixed anvil behavior so unauthorized level upgrades are refused
- Fixed anvil behavior so a different core cannot be applied to an already infused item

### Added

- Added a level system for compatible infusions
- Added support for upgrading an existing infusion in the anvil using the same Infusion Core
- Added support for infusion levels from I to V
- Added a configurable maximum level limit
- Added an internal hard cap at level V
- Added a dedicated config file:
  - `config/LoxyCraft/loxycraft.json`
- Added the `itemUpgrades` config section
- Added the ability to disable new item upgrades entirely
- Added the `infusionLevels` config section
- Added the ability to enable or disable only level upgrades
- Added a configurable XP cost for level upgrades
- Added the command:
  - `/loxycraft reload`

### Changed

- Changed the following effects so they can now scale with levels:
  - Resistance
  - Speed
  - Jump Boost
  - Strength
  - Haste
  - Luck
- Changed the following effects so they intentionally remain non-scaling:
  - Night Vision
  - Water Breathing
  - Fire Resistance
  - Slow Falling
  - Unbreakable
- Changed Unbreakable so it remains separate from the level system
- Changed Unbreakable so it remains compatible with one effect infusion

### Improved

- Improved compatible infusions so they can now progress beyond level I
- Improved server-side control over infusion levels
- Improved admin control by allowing infusion levels to be limited to the desired maximum
- Improved admin flexibility by allowing item upgrades to be disabled without deleting already infused items
- Improved configuration workflow with `/loxycraft reload`, allowing config reloads without restarting the game or server
- Improved tooltips so they now show levels for compatible infusions
- Improved already infused item behavior so they now automatically respect the configured level cap
- Improved effect limiting so when the maximum level is reduced, applied effects are capped to the new allowed maximum
- Improved fallback behavior so when levels are disabled, existing infusions are treated as level I

### Notes

- `itemUpgrades.enabled = false` blocks creation of new infusions and item upgrades in the anvil
- Already infused items are not removed when upgrades are disabled
- `infusionLevels.enabled = false` only blocks level upgrades
- A base infusion remains possible if `itemUpgrades.enabled = true`
- `maxLevel` cannot exceed 5
- Non-sensical levels such as Night Vision V or Fire Resistance V are intentionally refused
- A future update may add a system to reset or remove infusions

## 1.4.0

### Summary

This update adds a new late-game upgrade to LoxyCraft’s infusion system: the **Unbreakable** infusion, allowing compatible Netherite equipment to become unbreakable through a dedicated new core.

### Fixed

- Fixed multiple application of the Unbreakable infusion on the same item
- Fixed Unbreakable infusion application on incompatible items

### Added

- Added the **Unbreakable Infusion Core**
- Added a recipe for the Unbreakable Infusion Core:
  - Nether Star Block Core + Nether Star
- Added Unbreakable infusion support through the anvil
- Added support for making compatible Netherite equipment unbreakable
- Added a dedicated tooltip for items made unbreakable
- Added a dedicated texture for the Unbreakable Infusion Core

### Improved

- Improved Nether Star Block Core usefulness with a new late-game purpose
- Improved infusion flexibility by making the Unbreakable infusion compatible with existing effect infusions
- Improved upgrade combinations so one item can now have both an effect infusion and the Unbreakable upgrade
- Improved infusion workflow so the Unbreakable infusion can be applied before or after an effect infusion

### Notes

- The Unbreakable infusion is limited to Netherite armor, tools, and weapons
- The Unbreakable infusion does not replace effect infusions
- The Unbreakable infusion has no level: an item is either unbreakable or it is not
- The next planned update is 1.5.0, focused on configurable infusion levels

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
