# Dev's modpack guide

IP: `mc.doke.house`

## Installation

### 1. Download the modpack file

Click here to download the modpack file: [BoredSMP Client 1.2.1](https://www.dropbox.com/scl/fi/hy7zqqdsbv86p4yijk7oy/BoredSMP-Client-1.2.1.mrpack?rlkey=fxruq71zmq13coo0kys9ray05&st=5cubtz7w&dl=0)

### 2. Import into your launcher

**Modrinth**: "Add instance" → "Modpack base" → "Import modpack" → select the `.mrpack` file you just downloaded.

**Prism Launcher**: "Add instance" → "Import" → select the `.mrpack` file you just downloaded.

### 3. Updating

If you want to avoid losing custom keybinds, minimap data, etc, you can just manually install all new mods in the list below marked with "✨" to your current instance.

Alternatively, you can just manually copy over relevant folders from your old instance into the new instance. (i.e the `xaero` directory)

Otherwise, just follow the same installation steps above.

## Optimization guide (click to expand)
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

## Current mod list

| **Type**    | **Name**                                                                                                          | **Note**                                                  | **Environment** |
| ----------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- | --------------- |
| QoL         | [FTB Backups 3](https://modrinth.com/mod/ftb-backups-2)                                                           | Automated server world backups                            | Server          |
| Library     | [FTB Essentials (Forge & Fabric)](https://modrinth.com/mod/ftb-essentials)                                        | Required library for FTB mods                             | Both            |
| Library     | [FTB Library (NeoForge)](https://modrinth.com/mod/ftb-library-fabric)                                             | Required library for FTB mods                             | Both            |
| QoL         | [FTB Ultimine](https://modrinth.com/mod/ftb-ultimine-fabric)                                                      | Vein mining via keybind (default `~`)                     | Both            |
| Performance | [Clumps](https://modrinth.com/mod/clumps)                                                                         | Clumps XP orbs to reduce XP farm lag                     | Both            |
| Performance | [Concurrent Chunk Management Engine (NeoForge)](https://modrinth.com/mod/c2me-fabric)                             | Chunk loading performance for clients & servers           | Both            |
| QoL         | [LambDynamicLights](https://modrinth.com/mod/lambdynamiclights)                                                   | Dynamic light sources (e.g. held torches)                 | Client          |
| Performance | [Leaves Be Gone](https://modrinth.com/mod/leaves-be-gone)                                                         | Fast leaf decay after tree chopping                       | Both            |
| QoL         | [No More Phantoms](https://modrinth.com/mod/no-more-phantoms)                                                     | Adds a phantom membrane recipe                            | Both            |
| QoL         | [Visual Workbench](https://modrinth.com/mod/visual-workbench)                                                     | Items stay visible in crafting tables                     | Both            |
| QoL         | [Polymorph](https://modrinth.com/mod/polymorph/version/VEburL70)                                                   | Cycle through conflicting recipes                     | Both            |
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
| QoL         | [Better than Mending](https://modrinth.com/mod/better-than-mending)                                               | Mending QoL improvements                                  | Both            |
| Add-on      | [Brewin' And Chewin'](https://modrinth.com/mod/brewin-and-chewin)                                                 | Farmer's Delight drinks & food add-on                     | Both            |
| Content     | [Classic Pipes](https://modrinth.com/mod/classic-pipes)                                                           | Item transport; pairs well with Create                    | Both            |
| Library     | [Cloth Config API](https://modrinth.com/mod/cloth-config)                                                         | Config GUI library                                        | Both            |
| Library     | [Collective](https://modrinth.com/mod/collective)                                                                 | Shared library for Serilum mods                           | Both            |
| Content     | [Compressed Fuel](https://modrinth.com/mod/compressed-fuel)                                                       | Compressed fuel blocks for furnaces                       | Both            |
| Performance | [Configured Defaults](https://modrinth.com/mod/configured-defaults)                                               | Ships default configs/keybinds to users                   | Client          |
| QoL         | [Controlling](https://modrinth.com/mod/controlling)                                                               | Searchable keybind menu                                   | Client          |
| QoL         | [✨ Construction Wands Revived](https://modrinth.com/mod/construction-wands-revived)                               | Place lines or planes of blocks with a wand               | Both            |
| QoL         | [Corpse](https://modrinth.com/mod/corpse)                                                                         | Death drop protection preserving accessories              | Both            |
| Add-on      | [Corpse Curios Compatibility](https://modrinth.com/mod/corpse-x-curios-api-compat)                                | Corpse compatibility for Curios API                       | Both            |
| Content     | [Create](https://modrinth.com/mod/create)                                                                         | Kinetic automation & contraptions                         | Both            |
| Add-on      | [Create Deco](https://modrinth.com/mod/create-deco)                                                               | Decorative blocks for Create                              | Both            |
| Add-on      | [Create: Bells & Whistles](https://modrinth.com/mod/create-bells-and-whistles)                                    | Aesthetic additions for Create                            | Both            |
| Add-on      | [Create: Copycats+](https://modrinth.com/mod/copycats)                                                            | Expanded copycat blocks                                   | Both            |
| Add-on      | [Create: Dragons Plus](https://modrinth.com/mod/create-dragons-plus)                                              | Dragon-themed Create contraptions                         | Both            |
| Add-on      | [Create: Enchantment Industry](https://modrinth.com/mod/create-enchantment-industry)                              | Automates XP & enchanting with Create                     | Both            |
| Add-on      | [Create: Interiors](https://modrinth.com/mod/interiors)                                                           | Interior design blocks for Create                         | Both            |
| Add-on      | [Create: Steam 'n' Rails](https://modrinth.com/mod/create-steam-n-rails)                                          | Expanded trains & rails                                   | Both            |
| Add-on      | [✨ Create: Central Kitchen](https://modrinth.com/mod/create-central-kitchen)                                      | Food processing automation for Create & Farmer's Delight  | Both            |
| Add-on      | [✨ Create Compressed](https://modrinth.com/mod/create-compressed)                                                 | Compressed resource blocks for Create processing          | Both            |
| Add-on      | [✨ Create Connected](https://modrinth.com/mod/create-connected)                                                   | Connected textures for Create's cosmetic blocks           | Both          |
| Add-on      | [✨ Create Contraption Terminals](https://modrinth.com/mod/create-contraption-terminals)                           | Add control terminals to Create contraptions              | Both            |
| Add-on      | [✨ Create: Design 'n' Decor](https://modrinth.com/mod/create-design-n-decor)                                      | Decorative building blocks themed around Create           | Both            |
| Add-on      | [✨ Create: Dreams and Desires](https://modrinth.com/mod/create-dreams-and-desires)                                | Functional & decorative expansion for Create              | Both            |
| Add-on      | [✨ Create Food](https://modrinth.com/mod/create-food)                                                             | Food-themed processing and automation for Create          | Both            |
| Add-on      | [✨ Create Integrated Farming](https://modrinth.com/mod/create-integrated-farming)                                 | Automates crop farming using Create mechanics             | Both            |
| Add-on      | [✨ Create Power Loaders](https://modrinth.com/mod/create-power-loaders)                                           | Chunk loaders powered by Create's rotational force        | Both            |
| Add-on      | [✨ Create Railways Navigator](https://modrinth.com/mod/create-railways-navigator)                                 | Map and route planner for Create train networks           | Both            |
| Add-on      | [✨ Create Slice n Dice](https://modrinth.com/mod/slice-and-dice)                                                  | Farmer's Delight processing via Create machines           | Both            |
| Add-on      | [✨ Create Trading Floor](https://modrinth.com/mod/create-trading-floor)                                           | Automates villager trading with Create contraptions       | Both            |
| Add-on      | [✨ Create Ultimate Factory](https://modrinth.com/mod/create-ultimate-factory)                                     | End-game factory automation building blocks               | Both            |
| Library     | [Curios API](https://modrinth.com/mod/curios)                                                                     | Legacy trinket slot API (paired with Accessories)         | Both            |
| QoL         | [Cut Through](https://modrinth.com/mod/cut-through)                                                               | Attack through foliage                                    | Client          |
| QoL         | [Default Options](https://modrinth.com/mod/default-options)                                                       | Enforces default user options on first launch             | Client          |
| QoL         | [Distraction Free Recipes (EMI)](https://modrinth.com/mod/distraction-free-recipes)                               | Hides recipe viewer until searching                       | Client          |
| Performance | [Dynamic FPS](https://modrinth.com/mod/dynamic-fps)                                                               | Locks FPS when window inactive                            | Client          |
| QoL         | [EMI](https://modrinth.com/mod/emi)                                                                               | Recipe viewer; EMI family replaces vanilla JEI usage      | Both            |
| Add-on      | [EMIffect](https://modrinth.com/mod/emiffect)                                                                     | Shows potion effect sources in EMI                        | Both            |
| Add-on      | [EMI Enchanting](https://modrinth.com/mod/emi-enchanting)                                                         | Shows enchantment info in EMI                             | Both            |
| Add-on      | [EMI Loot](https://modrinth.com/mod/emi-loot)                                                                     | Shows loot tables in EMI                                  | Both            |
| Add-on      | [EMI Ores](https://modrinth.com/mod/emi-ores)                                                                     | Shows ore distribution in EMI                             | Both            |
| Add-on      | [EMI Professions (EMIP)](https://modrinth.com/mod/emi-professions-emip)                                           | Shows villager trades in EMI                              | Both            |
| QoL         | [Easy Anvils](https://modrinth.com/mod/easy-anvils)                                                               | Anvils keep items on exit                                 | Both            |
| QoL         | [Easy Magic](https://modrinth.com/mod/easy-magic)                                                                 | Enchanting tables keep lapis                              | Both            |
| Content     | [✨ Easy Mob Farm](https://modrinth.com/mod/easy-mob-farm)                                                         | Simple upgradeable blocks for automated mob farming       | Both            |
| Performance | [EntityCulling](https://modrinth.com/mod/entityculling)                                                           | Culls offscreen entities                                  | Client          |
| Content     | [Explorer's Compass](https://modrinth.com/mod/explorers-compass)                                                  | Structure finder utility                                  | Both            |
| Content     | [Farmer's Delight](https://modrinth.com/mod/farmers-delight)                                                      | Cooking & farming expansion                               | Both            |
| Performance | [Fastquit](https://modrinth.com/mod/fastquit)                                                                     | Faster world quit                                         | Client          |
| Performance | [Ferrite Core](https://modrinth.com/mod/ferrite-core)                                                             | Memory usage reduction                                    | Both            |
| Library     | [Forgified Fabric API](https://modrinth.com/mod/forgified-fabric-api)                                             | Fabric API shim for (Neo)Forge; Sinytra Connector dep     | Both            |
| Content     | [Functional Storage](https://modrinth.com/mod/functional-storage)                                                 | Modern Storage Drawers replacement                        | Both            |
| Add-on      | [More Functional Storage](https://modrinth.com/mod/more-functional-storage)                                       | Extra drawer types for Functional Storage                 | Both            |
| QoL         | [Fusion](https://modrinth.com/mod/fusion-connected-textures)                                                      | Connected textures support                                | Client          |
| Library     | [Fzzy Config](https://modrinth.com/mod/fzzy-config)                                                               | Config library                                            | Both            |
| Performance | [Gnetum](https://modrinth.com/mod/gnetum)                                                                         | HUD draw optimization                                     | Client          |
| Content     | [Hang Glider](https://modrinth.com/mod/hang-glider)                                                               | Low-tech elytra alternative                               | Both            |
| Performance | [ImmediatelyFast](https://modrinth.com/mod/immediatelyfast)                                                       | Misc. client rendering fastpaths                          | Client          |
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
| QoL         | [Just Enough Items (JEI)](https://modrinth.com/mod/jei)                                                           | Base recipe viewer (EMI depends on it)                    | Both            |
| Content     | [Just Hammers](https://modrinth.com/mod/just-hammers)                                                             | Balanced multi-block-breaking hammers                     | Both            |
| QoL         | [Just Zoom](https://modrinth.com/mod/just-zoom)                                                                   | Simple zoom keybind                                       | Client          |
| Library     | [Konkrete](https://modrinth.com/mod/konkrete)                                                                     | UI library                                                | Both            |
| Library     | [Kotlin for Forge](https://modrinth.com/mod/kotlin-for-forge)                                                     | Kotlin runtime for Forge mods                             | Both            |
| Performance | [Lithium](https://modrinth.com/mod/lithium)                                                                       | General game optimizations                                | Both            |
| QoL         | [Lootr](https://modrinth.com/mod/lootr)                                                                           | Per-user loot chests                                      | Both            |
| Add-on      | [Man of Many Planes](https://modrinth.com/mod/man-of-many-planes)                                                 | Extra Immersive Aircraft planes                           | Both            |
| Performance | [ModernFix](https://modrinth.com/mod/modernfix)                                                                   | Broad performance & memory patches                        | Both            |
| Library     | [Moonlight Lib](https://modrinth.com/mod/moonlight)                                                               | Library (Supplementaries dep)                             | Both            |
| Performance | [More Culling](https://modrinth.com/mod/moreculling)                                                              | Block/entity culling optimization                         | Both            |
| QoL         | [✨ Mouse Tweaks](https://modrinth.com/mod/mouse-tweaks)                                                           | Enhances inventory item drag & scroll behavior            | Client          |
| Content     | [Nature's Compass](https://modrinth.com/mod/natures-compass)                                                      | Biome finder utility                                      | Both            |
| Performance | [NetherPortalFix](https://modrinth.com/mod/netherportalfix)                                                       | Fixes nether portal linking bugs                          | Both            |
| QoL         | [✨ No Chat Reports](https://modrinth.com/mod/no-chat-reports)                                                     | Prevents chat messages from being reported to Mojang      | Both            |
| QoL         | [No Elytras](https://modrinth.com/mod/no-elytras)                                                                 | Disables elytra                                           | Both            |
| QoL         | [Not Enough Recipe Book](https://modrinth.com/mod/not-enough-recipe-book)                                         | Disables vanilla recipe book for perf                     | Both            |
| Library     | [OctoLib](https://modrinth.com/mod/octolib)                                                                       | Dependency library                                        | Both            |
| Library     | [oωo (owo-lib)](https://modrinth.com/mod/owo-lib)                                                                 | UI/config library                                         | Both            |
| Performance | [Packet Fixer](https://modrinth.com/mod/packet-fixer)                                                             | Server packet handling fixes                              | Both            |
| Library     | [PolyLib](https://modrinth.com/mod/polylib)                                                                       | Dependency library                                        | Both            |
| Library     | [Puzzles Lib](https://modrinth.com/mod/puzzles-lib)                                                               | Library (Easy Anvils/Easy Magic dep)                      | Both            |
| Content     | [Quark](https://modrinth.com/mod/quark)                                                                           | Modular vanilla+ additions                                | Both            |
| Content     | [Rechiseled](https://modrinth.com/mod/rechiseled)                                                                 | Extensive building block variants                         | Both            |
| Add-on      | [Rechiseled: Create](https://modrinth.com/mod/rechiseled-create)                                                  | Rechiseled variants of Create's cosmetic blocks           | Both            |
| Content     | [Relics](https://modrinth.com/mod/relics-mod)                                                                     | Trinket mod with unique upgradeable items                 | Both            |
| QoL         | [Right Click Harvest](https://modrinth.com/mod/right-click-harvest)                                               | Right-click to harvest & replant crops                    | Both            |
| Library     | [Searchables](https://modrinth.com/mod/searchables)                                                               | Search API (used by Controlling, JEI, etc.)               | Both            |
| QoL         | [Simple Voice Chat](https://modrinth.com/mod/simple-voice-chat)                                                   | Proximity voice chat                                      | Both            |
| Content     | [✨ Snad](https://modrinth.com/mod/snad)                                                                           | Sand variant that accelerates nearby crop growth          | Both            |
| Performance | [Sinytra Connector](https://modrinth.com/mod/connector)                                                           | Runs Fabric mods on NeoForge                              | Both            |
| Performance | [Sodium](https://modrinth.com/mod/sodium)                                                                         | Rendering optimization                                    | Client          |
| Performance | [Sodium Extra](https://modrinth.com/mod/sodium-extra)                                                             | Extra Sodium toggles                                      | Client          |
| Content     | [Sophisticated Backpacks](https://modrinth.com/mod/sophisticated-backpacks)                                       | Upgradeable backpacks                                     | Both            |
| Add-on      | [Sophisticated Backpacks Create Integration](https://modrinth.com/mod/sophisticated-backpacks-create-integration) | Create compatibility for Sophisticated Backpacks          | Both            |
| Library     | [Sophisticated Core](https://modrinth.com/mod/sophisticated-core)                                                 | Sophisticated mods dependency                             | Both            |
| QoL         | [Sound Physics Remastered](https://modrinth.com/mod/sound-physics-remastered)                                     | Realistic audio propagation & reverb                      | Both            |
| Content     | [Supplementaries](https://modrinth.com/mod/supplementaries)                                                       | Vanilla+ additions                                        | Both            |
| Library     | [SuperMartijn642's Core Lib](https://modrinth.com/mod/supermartijn642corelib)                                     | Rechiseled/Functional Storage dependency                  | Both            |
| Library     | [SuperMartijn642's Config Library](https://modrinth.com/mod/supermartijn642configlib)                             | Config library for SuperMartijn642 mods                   | Both            |
| Library     | [Titanium](https://modrinth.com/mod/titanium)                                                                     | Hrududu Industries library                                | Both            |
| Content     | [Tom's Simple Storage Mod](https://modrinth.com/mod/toms-storage)                                                 | Networked storage system                                  | Both            |
| QoL         | [✨ Trash Slot](https://modrinth.com/mod/trashslot)                                                                | Adds a dedicated item trash slot to the inventory         | Both          |
| Library     | [TxniLib](https://modrinth.com/mod/txnilib)                                                                       | Dependency library                                        | Both            |
| Library     | [✨ UltiCreate Compatibility](https://modrinth.com/mod/ulticreate-compatibility)                                   | Shared compatibility layer for UltiCreate addon mods      | Both            |
| Performance | [Vanillin](https://modrinth.com/mod/vanillin)                                                                     | Entity rendering optimization                             | Client          |
| Library     | [Zeta](https://modrinth.com/mod/zeta)                                                                             | Quark dependency                                          | Both            |
