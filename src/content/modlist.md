# Dev's modpack guide

IP: `mc.doke.house`

## Installation

### 1. Download the modpack file

Click here to download the modpack file: [BoredSMP Client 1.4.0](https://www.dropbox.com/scl/fi/jmwjkitawyewo7mkv6dib/BoredSMP-Client-1.4.0.mrpack?rlkey=zd5hm3gk4lt3ozz0mmrsitj8i&st=qqqhw1hj&dl=0)

### 2. Import into your launcher

**Modrinth**: "Add instance" → "Modpack base" → "Import modpack" → select the `.mrpack` file you just downloaded.

**Prism Launcher**: "Add instance" → "Import" → select the `.mrpack` file you just downloaded.

### 3. Updating

If you want to avoid losing custom keybinds, minimap data, etc, you can just manually install all new mods in the list below marked with "✨" to your current instance.

Alternatively, you can just manually copy over relevant folders from your old instance into the new instance. (i.e the `xaero` directory)

Otherwise, just follow the same installation steps above.

## Optimization guide (click to expand)

### Prerequisite: disable performance-intensive mods

If you run into any performance issues, I heavily reccomend disabling one or more of these mods:

- Iris Shaders (and Iris Flywheel Compat)
- Sound Physics Remastered
- LambDynamicLights
- Distant Horizons (if you use it)

### 1. Download & install GraalVM 25

Go to [graalvm.org/downloads](https://www.graalvm.org/downloads/), select **GraalVM 25** for your OS, and download the archive. Extract it to an appropriate location (`C:\Program Files\Java\` on Windows)

### 2. Point your launcher to GraalVM 25

**Modrinth**: Global settings → `Java installations` → `Java 25 location` → `Detect` → select entry with `GraalVM` in it 

**Prism Launcher**: Global preferences → `Java` → `Java installation` → `Detect` → select entry with `GraalVM` in it

If GraalVM isn't automatically detected, click "Browse" and manually navigate to the `bin` folder inside the directory you just extracted.

### 3. Allocate RAM

Increase your memory allocation to something sensible. **8–10 GB** is plenty for most setups, just don't exceed your system's total available RAM. For **Modrinth**, this is done under the "Default instance options" tab.

### 4. Set optimized Java arguments

Paste the following into the "Java Arguments" field: 

```
-XX:+UnlockExperimentalVMOptions -XX:+UnlockDiagnosticVMOptions -XX:+AlwaysActAsServerClassMachine -XX:+AlwaysPreTouch -XX:+DisableExplicitGC -XX:NmethodSweepActivity=1 -XX:ReservedCodeCacheSize=400M -XX:NonNMethodCodeHeapSize=12M -XX:ProfiledCodeHeapSize=194M -XX:NonProfiledCodeHeapSize=194M -XX:-DontCompileHugeMethods -XX:+PerfDisableSharedMem -XX:+UseFastUnorderedTimeStamps -XX:+EagerJVMCI -Djdk.graal.CompilerConfiguration=enterprise -Djdk.graal.TuneInlinerExploration=1 -XX:+UseFastUnorderedTimeStamps -XX:+UseCriticalJavaThreadPriority -XX:+UseStringDeduplication -XX:+UseAES -XX:+UseAESIntrinsics -XX:+UseFMA -XX:+UseLoopPredicate -XX:+RangeCheckElimination -XX:+OptimizeStringConcat -XX:+UseCompressedOops -XX:+UseThreadPriorities -XX:+OmitStackTraceInFastThrow -XX:+RewriteBytecodes -XX:+RewriteFrequentPairs -XX:+UseFPUForSpilling -XX:+UseVectorCmov -XX:+UseXMMForArrayCopy -XX:+EliminateLocks -XX:+DoEscapeAnalysis -XX:+AlignVector -XX:+OptimizeFill -XX:+EnableVectorSupport -XX:+UseCharacterCompareIntrinsics -XX:+UseCopySignIntrinsic -XX:+UseVectorStubs -XX:+UseFastJNIAccessors -XX:+UseInlineCaches -XX:+SegmentedCodeCache -XX:ThreadPriorityPolicy=1 -XX:+UseG1GC -XX:MaxGCPauseMillis=130 -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=28 -XX:G1HeapRegionSize=16M -XX:G1ReservePercent=20 -XX:G1MixedGCCountTarget=3 -XX:InitiatingHeapOccupancyPercent=10 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=0 -XX:SurvivorRatio=32 -XX:MaxTenuringThreshold=1 -XX:G1SATBBufferEnqueueingThresholdPercent=30 -XX:G1ConcMarkStepDurationMillis=5.0 -XX:AllocatePrefetchStyle=3 -XX:+UseCompactObjectHeaders
```

### 4. Ensure instance settings match

Navigate to the instance settings for the modpack itself and ensure its using the global settings you just configured. For **Prism Launcher**, you'll want to make sure the "Java Installation", "Memory", and "Java Arguments" fields in the instance settings are all NOT checked.

### 5. Launch the game!

⚠️ **If you run into any crashes:**

- Double check that the modpack instance itself is actually using the global settings you configured and is pointing to the correct Java installation (GraalVM 25).
- If you still encounter issues, try removing the `-XX:+UseCompactObjectHeaders` flag from the above arguments.

## Changelogs (click to expand)

### 1.4.0

- Updated NeoForge to `21.1.229`
- New: Create Unbreakable Pickaxe
- New: Create Unbreakable Netherite Axe
- New: Create Unbreakable Netherite Shovel
- New: Create Unbreakable Netherite Sword
- New: Create Unbreakable Netherite Paxel
- New: Create Nuclear
- New: Create Tracks
- New: Create Escalated
- New: Create Cobblestone
- New: Vista
- New: Vista Aeronautics Fix
- New: Create Propulsion Simulated
- New: Applied Energistics 2
- New: Applied Energistics 2 Wireless Terminals
- New: Rechiseled Applied Energistics 2
- New: AdvancedAE
- New: Extended AE
- New: ME Requester
- New: MEGA Cells
- New: AE2WTLib
- New: Applied Flux
- New: GuideME
- New: Create AE2 recipes
- New: Applied Create
- New: AE2 JEI Integration
- New: AE2 Network Analyser
- New: AEInfinityBooster
- New: EnderDrives
- New: Modular Bees
- New: Productive Bees
- New: Botany Pots
- New: Botany Trees
- New: Botany Pots Tiers
- New: Staaaaaaaaaaaack (Stxck)
- New: Handcrafted
- New: CC Tweaked
- New: CCC Bridge
- New: CC Sable
- New: Tom's Peripherals
- New: Advanced Peripherals
- New: AllTheCompressed
- New: Tool Belt
- New: Torchmaster
- New: Kubejs
- New: GeckoLib 4
- New: Glodium
- New: ResourcefulLib
- New: Rhino
- New: FTB JEI Extras
- Updated: Moonlight Lib (`1.21.1-3.0.7`)
- Updated: Supplementaries (`1.21.1-3.6.4`)
- Updated: EMI (`1.1.23+1.21.1+neoforge`)
- Updated: Immersive Melodies (`0.6.3+1.21.1`)
- Updated: Tesseract API (`1.11.12-1.21.1`)
- Updated: Relics (`0.12.3`)
- Removed: Vanillin
- Removed: Immersive Optimization
- Removed: Concurrent Chunk Management Engine (C2ME)

## Current mod list

| **Type**    | **Name**                                                                                                          | **Note**                                                  | **Environment** |
| ----------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- | --------------- |
| Add-on      | [✨ Create Unbreakable Pickaxe](https://modrinth.com/mod/create-unbreakable-pickaxe)                              | Unbreakable utility tool for Create workflows             | Both            |
| Add-on      | [✨ Create Unbreakable Netherite Axe](https://modrinth.com/mod/create-unbreakable-netherite-axe)                  | Unbreakable netherite axe add-on for Create tooling       | Both            |
| Add-on      | [✨ Create Unbreakable Netherite Shovel](https://modrinth.com/mod/create-unbreakable-netherite-shovel)            | Unbreakable netherite shovel add-on for Create tooling    | Both            |
| Add-on      | [✨ Create Unbreakable Netherite Sword](https://modrinth.com/mod/create-unbreakable-netherite-sword)              | Unbreakable netherite sword add-on for Create tooling     | Both            |
| Add-on      | [✨ Create Unbreakable Netherite Paxel](https://modrinth.com/mod/create-unbreakable-netherite-paxel)              | Unbreakable paxel utility for all-in-one mining           | Both            |
| Add-on      | [✨ Create Nuclear](https://modrinth.com/mod/create-nuclear)                                                       | Nuclear-themed machines and progression for Create         | Both            |
| Add-on      | [✨ Create Tracks](https://modrinth.com/mod/create-tracks)                                                         | Extra train track variants and rail components            | Both            |
| Add-on      | [✨ Create Escalated](https://modrinth.com/mod/create-escalated)                                                   | Higher-tier Create machines and automation parts          | Both            |
| Add-on      | [✨ Create Cobblestone](https://modrinth.com/mod/create-cobblestone)                                               | Cobblestone generation/processing add-on for Create       | Both            |
| Content     | [✨ Vista](https://modrinth.com/mod/vista)                                                                         | Visual/worldbuilding content expansion                    | Both            |
| Add-on      | [✨ Vista Aeronautics Fix](https://modrinth.com/mod/vista-aeronautics-fix)                                         | Compatibility fix between Vista and Create Aeronautics    | Both            |
| Add-on      | [✨ Create Propulsion Simulated](https://modrinth.com/mod/create-propulsion-simulated)                             | Simulated propulsion systems for Create contraptions      | Both            |
| Content     | [✨ Applied Energistics 2](https://modrinth.com/mod/ae2)                                                           | Digital storage and autocrafting network                  | Both            |
| Add-on      | [✨ Applied Energistics 2 Wireless Terminals](https://modrinth.com/mod/ae2wtlib)                                  | Wireless access terminals for AE2 networks                | Both            |
| Add-on      | [✨ Rechiseled Applied Energistics 2](https://modrinth.com/mod/rechiseled-applied-energistics-2)                  | Rechiseled block variants for AE2                         | Both            |
| Add-on      | [✨ AdvancedAE](https://modrinth.com/mod/advancedae)                                                               | Advanced components and automation upgrades for AE2       | Both            |
| Add-on      | [✨ Extended AE](https://modrinth.com/mod/extendedae)                                                              | Extra late-game AE2 devices and parts                     | Both            |
| Add-on      | [✨ ME Requester](https://modrinth.com/mod/me-requester)                                                           | Auto-request and stocking tool for AE2 systems            | Both            |
| Add-on      | [✨ MEGA Cells](https://modrinth.com/mod/mega-cells)                                                               | Massive-capacity storage cells for AE2                    | Both            |
| Library     | [✨ AE2WTLib](https://modrinth.com/mod/ae2wtlib)                                                                   | Library/API for AE2 wireless terminal add-ons             | Both            |
| Add-on      | [✨ Applied Flux](https://modrinth.com/mod/applied-flux)                                                           | Flux/energy integrations for AE2                          | Both            |
| QoL         | [✨ GuideME](https://modrinth.com/mod/guideme)                                                                     | In-game guidance and documentation tooling                | Both            |
| Add-on      | [✨ Create AE2 recipes](https://modrinth.com/mod/create-ae2-recipes)                                               | Recipe bridge between Create and AE2                      | Both            |
| Add-on      | [✨ Applied Create](https://modrinth.com/mod/applied-create)                                                       | Deeper interoperability between AE2 and Create            | Both            |
| Add-on      | [✨ AE2 JEI Integration](https://modrinth.com/mod/ae2-jei-integration)                                             | Exposes AE2 data via JEI/EMI recipe views                 | Both            |
| Add-on      | [✨ AE2 Network Analyser](https://modrinth.com/mod/ae2-network-analyser)                                           | Network diagnostics for AE2 channels and devices          | Both            |
| Add-on      | [✨ AEInfinityBooster](https://modrinth.com/mod/aeinfinitybooster)                                                 | Extended/near-infinite wireless terminal range            | Both            |
| Add-on      | [✨ EnderDrives](https://modrinth.com/mod/enderdrives)                                                             | Ender-themed storage drives for AE2                       | Both            |
| Add-on      | [✨ Modular Bees](https://modrinth.com/mod/modular-bees)                                                           | Additional bee mechanics and integrations                 | Both            |
| Content     | [✨ Productive Bees](https://modrinth.com/mod/productive-bees)                                                     | Bee-based resource automation and progression             | Both            |
| Content     | [✨ Botany Pots](https://modrinth.com/mod/botany-pots)                                                             | Automated crop growth in compact pots                     | Both            |
| Add-on      | [✨ Botany Trees](https://modrinth.com/mod/botany-trees)                                                           | Tree support expansion for Botany Pots                    | Both            |
| Add-on      | [✨ Botany Pots Tiers](https://modrinth.com/mod/botany-pots-tiers)                                                 | Tiered upgrades for Botany Pots                           | Both            |
| QoL         | [✨ Staaaaaaaaaaaack (Stxck)](https://modrinth.com/mod/stxck)                                                      | Increases stack-size quality-of-life options              | Both            |
| Content     | [✨ Handcrafted](https://modrinth.com/mod/handcrafted)                                                             | Decorative furniture and building props                   | Both            |
| Content     | [✨ CC Tweaked](https://modrinth.com/mod/cc-tweaked)                                                               | Programmable computers and turtles                        | Both            |
| Add-on      | [✨ CCC Bridge](https://modrinth.com/mod/ccc-bridge)                                                               | Compatibility/integration bridge for CC ecosystems        | Both            |
| Add-on      | [✨ CC Sable](https://modrinth.com/mod/cc-sable)                                                                   | CC integration content for Sable                          | Both            |
| Add-on      | [✨ Tom's Peripherals](https://modrinth.com/mod/toms-peripherals)                                                  | Additional peripherals for CC Tweaked                     | Both            |
| Add-on      | [✨ Advanced Peripherals](https://modrinth.com/mod/advanced-peripherals)                                           | More turtle/computer peripherals and APIs                | Both            |
| Content     | [✨ AllTheCompressed](https://modrinth.com/mod/allthecompressed)                                                   | Many compressed block tiers for automation                | Both            |
| QoL         | [✨ Tool Belt](https://modrinth.com/mod/tool-belt)                                                                 | Quick access utility belt for tools                       | Both            |
| QoL         | [✨ Torchmaster](https://modrinth.com/mod/torchmaster)                                                             | Spawn-proofing and torch utility blocks                   | Both            |
| Library     | [✨ Kubejs](https://modrinth.com/mod/kubejs)                                                                       | Scriptable data/recipe customization framework            | Both            |
| Library     | [✨ GeckoLib 4](https://modrinth.com/mod/geckolib)                                                                 | Animated model library used by many content mods          | Both            |
| Library     | [✨ Glodium](https://modrinth.com/mod/glodium)                                                                     | Dependency/library support for modern mods                | Both            |
| Library     | [✨ ResourcefulLib](https://modrinth.com/mod/resourceful-lib)                                                      | Team Resourceful dependency library                       | Both            |
| Library     | [✨ Rhino](https://modrinth.com/mod/rhino)                                                                         | JavaScript engine dependency for scripting mods           | Both            |
| Add-on      | [✨ FTB JEI Extras](https://modrinth.com/mod/ftb-jei-extras)                                                       | Extra JEI/EMI helper views and recipe tools               | Both            |
| Add-on      | [AdvancedLootInfo](https://modrinth.com/mod/advancedlootinfo)                                                     | Detailed loot tables for recipe viewers                   | Both            |
| Performance | [All The Leaks](https://modrinth.com/mod/all-the-leaks)                                                           | Detects and reports memory leaks                          | Both            |
| Content     | [Almanac](https://modrinth.com/mod/almanac)                                                                       | In-game almanac with crop/biome info                      | Both            |
| Content     | [Apothic Spawners](https://modrinth.com/mod/apothic-spawners)                                                     | Configurable, upgradeable mob spawners                    | Both            |
| QoL         | [AttributeFix](https://modrinth.com/mod/attributefix)                                                             | Removes hardcoded attribute caps                          | Both            |
| Performance | [BadOptimizations](https://modrinth.com/mod/badoptimizations)                                                     | Misc client-side optimizations                            | Client          |
| Content     | [Baubley Heart Canisters](https://modrinth.com/mod/baubley-heart-canisters)                                       | Craftable max-HP-increasing canisters                     | Both            |
| Content     | [Better Beacons](https://modrinth.com/mod/better-beacons)                                                         | Expanded beacon effects and ranges                        | Both            |
| QoL         | [Better Compatibility Checker](https://modrinth.com/mod/better-compatibility-checker)                             | Warns clients of mismatched server mods                   | Both            |
| QoL         | [BetterF3](https://modrinth.com/mod/betterf3)                                                                     | Customizable F3 debug overlay                             | Client          |
| Library     | [Bookshelf](https://modrinth.com/mod/bookshelf-lib)                                                               | Darkhax dependency library                                | Both            |
| Library     | [Cerbons API](https://modrinth.com/mod/cerbons-api)                                                               | Dependency library                                        | Both            |
| Performance | [Chunky](https://modrinth.com/mod/chunky)                                                                         | Pre-generates chunks to reduce live-load lag              | Both            |
| Add-on      | [ChunkyBorder](https://modrinth.com/mod/chunkyborder)                                                             | World border integration for Chunky                       | Both            |
| Library     | [Configurable](https://modrinth.com/mod/configurable)                                                             | Config library                                            | Both            |
| Performance | [Continuity](https://modrinth.com/mod/continuity)                                                                 | Connected texture support                                 | Client          |
| Library     | [CoroUtil](https://modrinth.com/mod/coroutil)                                                                     | Corosus mods dependency library                           | Both            |
| QoL         | [Crafting Tweaks](https://modrinth.com/mod/crafting-tweaks)                                                       | Crafting grid management QoL                              | Both            |
| QoL         | [Crash Assistant](https://modrinth.com/mod/crash-assistant)                                                       | Surfaces and helps report crashes                         | Client          |
| Add-on      | [Create Aeronautics](https://modrinth.com/mod/create-aeronautics)                                                 | Flying contraptions for Create                            | Both            |
| Add-on      | [Create Aeronautics – Rechiseled Compat](https://modrinth.com/mod/create-aeronautics-rechiseled-compat)         | Rechiseled compatibility for Create Aeronautics           | Both            |
| Add-on      | [Create Crafts & Additions](https://modrinth.com/mod/createaddition)                                              | Flying contraptions for Create                            | Both            |
| QoL         | [Create touchpad scrolling fix](https://modrinth.com/mod/create-touchpad-scrolling-fix)                          | Fixes Create scroll inputs on laptop touchpads            | Client          |
| Add-on      | [Create: Enchantable Machinery](https://modrinth.com/mod/create-enchantable-machinery)                           | Allows enchanting Create machinery                        | Both            |
| QoL         | [Distinguished Potions](https://modrinth.com/mod/distinguished-potions)                                           | Visually differentiates potion variants                   | Client          |
| Library     | [DragonLib](https://modrinth.com/mod/dragonlib)                                                                   | Dependency library                                        | Both            |
| QoL         | [Durability Tooltip](https://modrinth.com/mod/durability-tooltip)                                                 | Shows item durability in tooltips                         | Client          |
| QoL         | [Effect Descriptions](https://modrinth.com/mod/effect-descriptions)                                               | Tooltip descriptions for status effects                   | Both            |
| QoL         | [EnchantmentDescriptions](https://modrinth.com/mod/enchantment-descriptions)                                      | Tooltip descriptions for enchantments                     | Both            |
| Add-on      | [Extra Mod Integrations](https://modrinth.com/mod/extra-mod-integrations)                                         | Cross-mod recipe integrations for EMI                     | Both            |
| QoL         | [FallingTree](https://modrinth.com/mod/falling-tree)                                                              | Chops whole trees with one cut                            | Both            |
| Performance | [Fast IP Ping](https://modrinth.com/mod/fast-ip-ping)                                                             | Speeds up server list ping                                | Client          |
| Performance | [Fast Item Frames](https://modrinth.com/mod/fast-item-frames)                                                     | Optimizes item frame rendering                            | Both            |
| Performance | [Fast Paintings](https://modrinth.com/mod/fast-paintings)                                                         | Optimizes painting rendering                              | Both            |
| Performance | [Fast Suite](https://modrinth.com/mod/fast-suite)                                                                 | Bundle of misc fast-tick fixes                            | Both            |
| Performance | [Fast Workbench](https://modrinth.com/mod/fastworkbench)                                                          | Optimizes crafting table tick                             | Both            |
| Performance | [FastFurnace](https://modrinth.com/mod/fastfurnace)                                                               | Optimizes furnace tick                                    | Both            |
| Content     | [Hostile Neural Networks](https://modrinth.com/mod/hostile-neural-networks)                                       | Simulate captured mobs to farm drops                      | Both            |
| Content     | [Immersive Melodies](https://modrinth.com/mod/immersive-melodies)                                                 | Playable musical instruments                              | Both            |
| QoL         | [ItemLocks](https://modrinth.com/mod/itemlocks)                                                                   | Lock inventory slots from being moved                     | Client          |
| Add-on      | [Just Enough Archaeology](https://modrinth.com/mod/just-enough-archaeology)                                       | Shows archaeology loot in EMI/JEI                         | Both            |
| Add-on      | [Just Enough Resources](https://modrinth.com/mod/just-enough-resources)                                           | Shows mob/world data in recipe viewers                    | Both            |
| Performance | [Let Me Despawn](https://modrinth.com/mod/let-me-despawn)                                                         | Lets mobs despawn properly to reduce entity load          | Both            |
| QoL         | [Lighty](https://modrinth.com/mod/lighty)                                                                         | Light-level overlay for mob spawning                      | Client          |
| QoL         | [Load My F\*\*\*ing Tags](https://modrinth.com/mod/load-my-tags)                                               | Forces stubborn data tags to load                         | Both            |
| Content     | [Mob Grinding Utils](https://modrinth.com/mod/mob-grinding-utils)                                                 | Mob farm utility blocks and items                         | Both            |
| QoL         | [Model Gap Fix](https://modrinth.com/mod/modelgapfix)                                                             | Fixes block-model rendering gaps                          | Client          |
| QoL         | [MoreMouseTweaks](https://modrinth.com/mod/moremousetweaks)                                                       | Adds further inventory mouse interactions                 | Client          |
| Add-on      | [Mouse Tweaks x ItemLocks Compat](https://modrinth.com/mod/mousetweaks-itemlocks-compat)                         | Compatibility patch between Mouse Tweaks and ItemLocks    | Client          |
| Add-on      | [MouseTweaks x Accessories Fix](https://modrinth.com/mod/mousetweaks-accessories-fix)                            | Fixes Mouse Tweaks behavior with Accessories slots        | Client          |
| QoL         | [NBT Autocomplete](https://modrinth.com/mod/nbt-autocomplete)                                                     | Autocompletes NBT in commands                             | Client          |
| QoL         | [NeoAuth](https://modrinth.com/mod/neoauth)                                                                       | Microsoft account auth helper                             | Client          |
| QoL         | [Neruina](https://modrinth.com/mod/neruina)                                                                       | Prevents crashes from ticking entity errors               | Both            |
| QoL         | [Overflowing Bars](https://modrinth.com/mod/overflowing-bars)                                                     | Stacks HP/armor/XP bars instead of shrinking icons        | Client          |
| Library     | [Particle Core](https://modrinth.com/mod/particle-core)                                                           | Particle dependency library                               | Both            |
| Library     | [Placebo](https://modrinth.com/mod/placebo)                                                                       | Shadows_of_Fire dependency library                        | Both            |
| Library     | [PrickleMC](https://modrinth.com/mod/pricklemc)                                                                   | Dependency library                                        | Both            |
| QoL         | [Redirected](https://modrinth.com/mod/redirected)                                                                 | Redirects deprecated/missing references                   | Both            |
| QoL         | [Reese's Sodium Options](https://modrinth.com/mod/reeses-sodium-options)                                          | Improved Sodium video options menu                        | Client          |
| QoL         | [Resource Pack Overrides](https://modrinth.com/mod/resource-pack-overrides)                                       | Per-pack settings & enable defaults                       | Client          |
| Content     | [Sable](https://modrinth.com/mod/sable)                                                                           | Sculk-themed dimension/content                            | Both            |
| Performance | [Saturn](https://modrinth.com/mod/saturn)                                                                         | Memory & GC optimizations                                 | Both            |
| Performance | [ServerCore](https://modrinth.com/mod/servercore)                                                                 | Server-side performance tweaks                            | Server          |
| QoL         | [Status Effect Bars](https://modrinth.com/mod/status-effect-bars)                                                 | Visual duration bars for status effects                   | Client          |
| QoL         | [Stylish Effects](https://modrinth.com/mod/stylish-effects)                                                       | Customizable potion effect HUD                            | Client          |
| Library     | [Tesseract API](https://modrinth.com/mod/tesseract-api)                                                           | Dependency library                                        | Both            |
| QoL         | [Too Fast](https://modrinth.com/mod/too-fast)                                                                     | Removes vanilla "moving too fast" check                   | Both            |
| Add-on      | [TooManyRecipeViewers](https://modrinth.com/mod/too-many-recipe-viewers)                                          | Compatibility shim between EMI/JEI/REI                    | Both            |
| QoL         | [Tooltip overhaul](https://modrinth.com/mod/tooltip-overhaul)                                                     | Visually improved item tooltips                           | Client          |
| QoL         | [What Are They Up To](https://modrinth.com/mod/watut)                                                             | Shows what other players are doing                        | Both            |
| Content     | [WorldEdit](https://modrinth.com/mod/worldedit)                                                                   | In-game world editing toolset                             | Both            |
| QoL         | [Xaero's Minimap](https://modrinth.com/mod/xaeros-minimap)                                                        | Customizable minimap with waypoints                       | Client          |
| QoL         | [Xaero's World Map](https://modrinth.com/mod/xaeros-world-map)                                                    | Persistent fullscreen world map                           | Client          |
| Add-on      | [XaeroPlus](https://modrinth.com/mod/xaeroplus)                                                                   | Extends Xaero's Minimap & World Map                       | Client          |
| QoL         | [Yeetus Experimentus](https://modrinth.com/mod/yeetus-experimentus)                                               | Removes the experimental settings warning                 | Both            |
| Performance | [spark](https://modrinth.com/mod/spark)                                                                           | In-game performance profiler                              | Both            |
| Library     | [Accessories](https://modrinth.com/mod/accessories)                                                               | Modern equipment API; preferred by newer mods             | Both            |
| Library     | [Accessories Compatibility Layer](https://modrinth.com/mod/accessories-compat-layer)                              | Bridges Accessories with Curios-dependent mods            | Both            |
| Add-on      | [Accessorify](https://modrinth.com/mod/accessorify)                                                               | Makes vanilla items equippable as accessories             | Both            |
| QoL         | [Amendments](https://modrinth.com/mod/amendments)                                                                 | Adds function to vanilla blocks; requires Supplementaries | Both            |
| QoL         | [AppleSkin](https://modrinth.com/mod/appleskin)                                                                   | Hunger HUD improvements                                   | Client          |
| Library     | [Architectury](https://modrinth.com/mod/architectury-api)                                                         | Cross-loader compat library                               | Both            |
| Content     | [Artifacts](https://modrinth.com/mod/artifacts)                                                                   | Trinkets with unique effects                              | Both            |
| Library     | [BaguetteLib](https://modrinth.com/mod/baguettelib)                                                               | Dependency library (Beltborne Lanterns)                   | Both            |
| Library     | [Balm](https://modrinth.com/mod/balm)                                                                             | Fabric/Forge abstraction library                          | Both            |
| Content     | [Beltborne Lanterns](https://modrinth.com/mod/beltborne-lanterns)                                                 | Lanterns that hang from your belt                         | Both            |
| Add-on      | [Beltborne Lanterns: Accessories Layer](https://modrinth.com/mod/beltborne-lanterns-accessories)                  | Accessories API integration for Beltborne Lanterns        | Both            |
| QoL         | [BetterThanMending](https://modrinth.com/mod/better-than-mending)                                                 | Mending QoL improvements                                  | Both            |
| Add-on      | [Brewin' And Chewin'](https://modrinth.com/mod/brewin-and-chewin)                                                 | Farmer's Delight drinks & food add-on                     | Both            |
| Content     | [Classic Pipes](https://modrinth.com/mod/classic-pipes)                                                           | Item transport; pairs well with Create                    | Both            |
| Library     | [Cloth Config v15 API](https://modrinth.com/mod/cloth-config)                                                     | Config GUI library                                        | Both            |
| Performance | [Clumps](https://modrinth.com/mod/clumps)                                                                         | Clumps XP orbs to reduce XP farm lag                      | Both            |
| Library     | [Collective](https://modrinth.com/mod/collective)                                                                 | Shared library for Serilum mods                           | Both            |
| Content     | [Compressed Fuel](https://modrinth.com/mod/compressed-fuel)                                                       | Compressed fuel blocks for furnaces                       | Both            |
| Performance | [Configured Defaults](https://modrinth.com/mod/configured-defaults)                                               | Ships default configs/keybinds to users                   | Client          |
| QoL         | [Construction Wands Revived](https://modrinth.com/mod/construction-wands-revived)                                 | Place lines or planes of blocks with a wand               | Both            |
| QoL         | [Controlling](https://modrinth.com/mod/controlling)                                                               | Searchable keybind menu                                   | Client          |
| QoL         | [Corpse](https://modrinth.com/mod/corpse)                                                                         | Death drop protection preserving accessories              | Both            |
| Add-on      | [Corpse Curios Compatibility](https://modrinth.com/mod/corpse-x-curios-api-compat)                                | Corpse compatibility for Curios API                       | Both            |
| Content     | [Create](https://modrinth.com/mod/create)                                                                         | Kinetic automation & contraptions                         | Both            |
| Add-on      | [Create Compressed](https://modrinth.com/mod/create-compressed)                                                   | Compressed resource blocks for Create processing          | Both            |
| Add-on      | [Create Contraption Terminals](https://modrinth.com/mod/create-contraption-terminals)                             | Add control terminals to Create contraptions              | Both            |
| Add-on      | [Create Deco](https://modrinth.com/mod/create-deco)                                                               | Decorative blocks for Create                              | Both            |
| Add-on      | [Create Railways Navigator](https://modrinth.com/mod/create-railways-navigator)                                   | Map and route planner for Create train networks           | Both            |
| Add-on      | [Create Slice & Dice](https://modrinth.com/mod/slice-and-dice)                                                    | Farmer's Delight processing via Create machines           | Both            |
| Add-on      | [Create: Bells & Whistles](https://modrinth.com/mod/create-bells-and-whistles)                                    | Aesthetic additions for Create                            | Both            |
| Add-on      | [Create: Central Kitchen](https://modrinth.com/mod/create-central-kitchen)                                        | Food processing automation for Create & Farmer's Delight  | Both            |
| Add-on      | [Create: Connected](https://modrinth.com/mod/create-connected)                                                    | Connected textures for Create's cosmetic blocks           | Both            |
| Add-on      | [Create: Copycats+](https://modrinth.com/mod/copycats)                                                            | Expanded copycat blocks                                   | Both            |
| Add-on      | [Create: Dragons Plus](https://modrinth.com/mod/create-dragons-plus)                                              | Dragon-themed Create contraptions                         | Both            |
| Add-on      | [Create: Dreams n' Desires](https://modrinth.com/mod/create-dreams-and-desires)                                   | Functional & decorative expansion for Create              | Both            |
| Add-on      | [Create: Enchantment Industry](https://modrinth.com/mod/create-enchantment-industry)                              | Automates XP & enchanting with Create                     | Both            |
| Add-on      | [Create: Food](https://modrinth.com/mod/create-food)                                                              | Food-themed processing and automation for Create          | Both            |
| Add-on      | [Create: Integrated Farming](https://modrinth.com/mod/create-integrated-farming)                                  | Automates crop farming using Create mechanics             | Both            |
| Add-on      | [Create: Interiors](https://modrinth.com/mod/interiors)                                                           | Interior design blocks for Create                         | Both            |
| Add-on      | [Create: Power Loader](https://modrinth.com/mod/create-power-loaders)                                             | Chunk loaders powered by Create's rotational force        | Both            |
| Add-on      | [Create: Steam 'n' Rails](https://modrinth.com/mod/create-steam-n-rails)                                          | Expanded trains & rails                                   | Both            |
| Add-on      | [Create: Trading Floor](https://modrinth.com/mod/create-trading-floor)                                            | Automates villager trading with Create contraptions       | Both            |
| Add-on      | [Create: Ultimate Factory](https://modrinth.com/mod/create-ultimate-factory)                                      | End-game factory automation building blocks               | Both            |
| Library     | [Curios API](https://modrinth.com/mod/curios)                                                                     | Legacy trinket slot API (paired with Accessories)         | Both            |
| QoL         | [Cut Through](https://modrinth.com/mod/cut-through)                                                               | Attack through foliage                                    | Client          |
| QoL         | [Default Options](https://modrinth.com/mod/default-options)                                                       | Enforces default user options on first launch             | Client          |
| Add-on      | [Design n' Decor](https://modrinth.com/mod/create-design-n-decor)                                                 | Decorative building blocks themed around Create           | Both            |
| QoL         | [EMI](https://modrinth.com/mod/emi)                                                                               | Recipe viewer; primary recipe browser                     | Both            |
| Add-on      | [EMI Enchanting](https://modrinth.com/mod/emi-enchanting)                                                         | Shows enchantment info in EMI                             | Both            |
| Add-on      | [EMI Loot](https://modrinth.com/mod/emi-loot)                                                                     | Shows loot tables in EMI                                  | Both            |
| Add-on      | [EMI Ores](https://modrinth.com/mod/emi-ores)                                                                     | Shows ore distribution in EMI                             | Both            |
| Add-on      | [EMI Professions (EMIP)](https://modrinth.com/mod/emi-professions-emip)                                           | Shows villager trades in EMI                              | Both            |
| Add-on      | [EMIffect](https://modrinth.com/mod/emiffect)                                                                     | Shows potion effect sources in EMI                        | Both            |
| QoL         | [Easy Anvils](https://modrinth.com/mod/easy-anvils)                                                               | Anvils keep items on exit                                 | Both            |
| QoL         | [Easy Magic](https://modrinth.com/mod/easy-magic)                                                                 | Enchanting tables keep lapis                              | Both            |
| Content     | [Easy Mob Farm](https://modrinth.com/mod/easy-mob-farm)                                                           | Simple upgradeable blocks for automated mob farming       | Both            |
| Performance | [EntityCulling](https://modrinth.com/mod/entityculling)                                                           | Culls offscreen entities                                  | Client          |
| Content     | [Explorer's Compass](https://modrinth.com/mod/explorers-compass)                                                  | Structure finder utility                                  | Both            |
| QoL         | [FTB Backups 3](https://modrinth.com/mod/ftb-backups-2)                                                           | Automated server world backups                            | Server          |
| Library     | [FTB Essentials](https://modrinth.com/mod/ftb-essentials)                                                         | Required library for FTB mods                             | Both            |
| Library     | [FTB Library](https://modrinth.com/mod/ftb-library-fabric)                                                        | Required library for FTB mods                             | Both            |
| QoL         | [FTB Ultimine](https://modrinth.com/mod/ftb-ultimine-fabric)                                                      | Vein mining via keybind (default `~`)                     | Both            |
| Content     | [Farmer's Delight](https://modrinth.com/mod/farmers-delight)                                                      | Cooking & farming expansion                               | Both            |
| Performance | [Fastquit](https://modrinth.com/mod/fastquit)                                                                     | Faster world quit                                         | Client          |
| Performance | [Ferrite Core](https://modrinth.com/mod/ferrite-core)                                                             | Memory usage reduction                                    | Both            |
| Library     | [Forgified Fabric API](https://modrinth.com/mod/forgified-fabric-api)                                             | Fabric API shim for (Neo)Forge; Sinytra Connector dep     | Both            |
| Content     | [Functional Storage](https://modrinth.com/mod/functional-storage)                                                 | Modern Storage Drawers replacement                        | Both            |
| QoL         | [Fusion](https://modrinth.com/mod/fusion-connected-textures)                                                      | Connected textures support                                | Client          |
| Library     | [Fzzy Config](https://modrinth.com/mod/fzzy-config)                                                               | Config library                                            | Both            |
| Performance | [Gnetum](https://modrinth.com/mod/gnetum)                                                                         | HUD draw optimization                                     | Client          |
| Content     | [Hang Glider](https://modrinth.com/mod/hang-glider)                                                               | Low-tech elytra alternative                               | Both            |
| Performance | [ImmediatelyFast](https://modrinth.com/mod/immediatelyfast)                                                       | Misc client rendering fastpaths                           | Client          |
| Content     | [Immersive Aircraft](https://modrinth.com/mod/immersive-aircraft)                                                 | Flyable aircraft                                          | Both            |
| Add-on      | [Immersive Aircraft: Better Engines](https://modrinth.com/mod/immersive-aircraft-better-engines)                  | Adds fuel variety to Immersive Aircraft                   | Both            |
| Content     | [Immersive Armors](https://modrinth.com/mod/immersive-armors)                                                     | Thematic armor sets                                       | Both            |
| Content     | [Immersive Paintings](https://modrinth.com/mod/immersive-paintings)                                               | Custom paintings from images                              | Both            |
| Performance | [Iris](https://modrinth.com/mod/iris)                                                                             | Shader support                                            | Client          |
| Performance | [Iris Flywheel Compat](https://modrinth.com/mod/iris-flywheel-compat)                                             | Makes Create's Flywheel renderer play nice with Iris      | Client          |
| Performance | [Ixeris](https://modrinth.com/mod/ixeris)                                                                         | Event & input optimization                                | Client          |
| QoL         | [Jade](https://modrinth.com/mod/jade)                                                                             | Block/entity tooltip overlay                              | Both            |
| Add-on      | [Jade Addons](https://modrinth.com/mod/jade-addons-forge)                                                         | Adds Create/mod compatibility to Jade                     | Both            |
| Library     | [JamLib](https://modrinth.com/mod/jamlib)                                                                         | Dependency library                                        | Both            |
| Add-on      | [Just Enough Breeding](https://modrinth.com/mod/justenoughbreeding)                                               | Shows mob breeding requirements in EMI/JEI                | Both            |
| Content     | [Just Hammers](https://modrinth.com/mod/just-hammers)                                                             | Balanced multi-block-breaking hammers                     | Both            |
| QoL         | [Just Zoom](https://modrinth.com/mod/just-zoom)                                                                   | Simple zoom keybind                                       | Client          |
| Library     | [Konkrete](https://modrinth.com/mod/konkrete)                                                                     | UI library                                                | Both            |
| Library     | [Kotlin for Forge](https://modrinth.com/mod/kotlin-for-forge)                                                     | Kotlin runtime for Forge mods                             | Both            |
| QoL         | [LambDynamicLights](https://modrinth.com/mod/lambdynamiclights)                                                   | Dynamic light sources (e.g. held torches)                 | Client          |
| Performance | [Lithium](https://modrinth.com/mod/lithium)                                                                       | General game optimizations                                | Both            |
| QoL         | [Lootr](https://modrinth.com/mod/lootr)                                                                           | Per-user loot chests                                      | Both            |
| Add-on      | [Man of Many Planes](https://modrinth.com/mod/man-of-many-planes)                                                 | Extra Immersive Aircraft planes                           | Both            |
| Performance | [ModernFix](https://modrinth.com/mod/modernfix)                                                                   | Broad performance & memory patches                        | Both            |
| Library     | [Moonlight Lib](https://modrinth.com/mod/moonlight)                                                               | Library (Supplementaries dep)                             | Both            |
| Performance | [More Culling](https://modrinth.com/mod/moreculling)                                                              | Block/entity culling optimization                         | Both            |
| Add-on      | [More Functional Storage](https://modrinth.com/mod/more-functional-storage)                                       | Extra drawer types for Functional Storage                 | Both            |
| QoL         | [Mouse Tweaks](https://modrinth.com/mod/mouse-tweaks)                                                             | Enhances inventory item drag & scroll behavior            | Client          |
| Content     | [Nature's Compass](https://modrinth.com/mod/natures-compass)                                                      | Biome finder utility                                      | Both            |
| Performance | [NetherPortalFix](https://modrinth.com/mod/netherportalfix)                                                       | Fixes nether portal linking bugs                          | Both            |
| QoL         | [No Chat Reports](https://modrinth.com/mod/no-chat-reports)                                                       | Prevents chat messages from being reported to Mojang      | Both            |
| QoL         | [No Elytras](https://modrinth.com/mod/no-elytras)                                                                 | Disables elytra                                           | Both            |
| QoL         | [No More Phantoms](https://modrinth.com/mod/no-more-phantoms)                                                     | Adds a phantom membrane recipe                            | Both            |
| QoL         | [Not Enough Recipe Book](https://modrinth.com/mod/not-enough-recipe-book)                                         | Disables vanilla recipe book for perf                     | Both            |
| Library     | [OctoLib](https://modrinth.com/mod/octolib)                                                                       | Dependency library                                        | Both            |
| Performance | [PacketFixer](https://modrinth.com/mod/packet-fixer)                                                              | Server packet handling fixes                              | Both            |
| Library     | [PolyLib](https://modrinth.com/mod/polylib)                                                                       | Dependency library                                        | Both            |
| QoL         | [Polymorph](https://modrinth.com/mod/polymorph)                                                                   | Cycle through conflicting recipes                         | Both            |
| Library     | [Puzzles Lib](https://modrinth.com/mod/puzzles-lib)                                                               | Library (Easy Anvils/Easy Magic dep)                      | Both            |
| Content     | [Quark](https://modrinth.com/mod/quark)                                                                           | Modular vanilla+ additions                                | Both            |
| Content     | [Rechiseled](https://modrinth.com/mod/rechiseled)                                                                 | Extensive building block variants                         | Both            |
| Add-on      | [Rechiseled: Create](https://modrinth.com/mod/rechiseled-create)                                                  | Rechiseled variants of Create's cosmetic blocks           | Both            |
| Content     | [Relics](https://modrinth.com/mod/relics-mod)                                                                     | Trinket mod with unique upgradeable items                 | Both            |
| QoL         | [Right Click Harvest](https://modrinth.com/mod/right-click-harvest)                                               | Right-click to harvest & replant crops                    | Both            |
| Library     | [Searchables](https://modrinth.com/mod/searchables)                                                               | Search API (used by Controlling, etc.)                    | Both            |
| QoL         | [Simple Voice Chat](https://modrinth.com/mod/simple-voice-chat)                                                   | Proximity voice chat                                      | Both            |
| Performance | [Sinytra Connector](https://modrinth.com/mod/connector)                                                           | Runs Fabric mods on NeoForge                              | Both            |
| Content     | [Snad](https://modrinth.com/mod/snad)                                                                             | Sand variant that accelerates nearby crop growth          | Both            |
| Performance | [Sodium](https://modrinth.com/mod/sodium)                                                                         | Rendering optimization                                    | Client          |
| Performance | [Sodium Extra](https://modrinth.com/mod/sodium-extra)                                                             | Extra Sodium toggles                                      | Client          |
| Content     | [Sophisticated Backpacks](https://modrinth.com/mod/sophisticated-backpacks)                                       | Upgradeable backpacks                                     | Both            |
| Add-on      | [Sophisticated Backpacks Create Integration](https://modrinth.com/mod/sophisticated-backpacks-create-integration) | Create compatibility for Sophisticated Backpacks          | Both            |
| Library     | [Sophisticated Core](https://modrinth.com/mod/sophisticated-core)                                                 | Sophisticated mods dependency                             | Both            |
| QoL         | [Sound Physics Remastered](https://modrinth.com/mod/sound-physics-remastered)                                     | Realistic audio propagation & reverb                      | Both            |
| Library     | [SuperMartijn642's Config Library](https://modrinth.com/mod/supermartijn642configlib)                             | Config library for SuperMartijn642 mods                   | Both            |
| Library     | [SuperMartijn642's Core Lib](https://modrinth.com/mod/supermartijn642corelib)                                     | Rechiseled/Functional Storage dependency                  | Both            |
| Content     | [Supplementaries](https://modrinth.com/mod/supplementaries)                                                       | Vanilla+ additions                                        | Both            |
| Library     | [Titanium](https://modrinth.com/mod/titanium)                                                                     | Hrududu Industries library                                | Both            |
| Content     | [Tom's Simple Storage Mod](https://modrinth.com/mod/toms-storage)                                                 | Networked storage system                                  | Both            |
| QoL         | [TrashSlot](https://modrinth.com/mod/trashslot)                                                                   | Adds a dedicated item trash slot to the inventory         | Both            |
| Library     | [TxniLib](https://modrinth.com/mod/txnilib)                                                                       | Dependency library                                        | Both            |
| Library     | [UltiCreate Compatibility](https://modrinth.com/mod/ulticreate-compatibility)                                     | Shared compatibility layer for UltiCreate addon mods      | Both            |
| QoL         | [Visual Workbench](https://modrinth.com/mod/visual-workbench)                                                     | Items stay visible in crafting tables                     | Both            |
| Library     | [Zeta](https://modrinth.com/mod/zeta)                                                                             | Quark dependency                                          | Both            |
| Library     | [oωo (owo-lib)](https://modrinth.com/mod/owo-lib)                                                                 | UI/config library                                         | Both            |