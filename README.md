# Expedition Board

A replayable Minecraft adventure from Dadcraft73. Gather rotating supplies, tackle biome-themed combat events, explore a generated region and bank relics together.

**Current playtest: 0.3.0 · Minecraft Java Edition 26.3 · eight objectives.** Play solo or as one cooperative team. One expedition runs at a time; the four selectable colors do not create simultaneous competing matches. This is a work in progress, and human testing is still assessing pacing, combat and structures.

## Downloads

| Download | Use it for |
|---|---|
| [Fresh server world](https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.14/Expedition-Coop-Server-0.2.14.zip) | Base world for a new installation. Apply the 0.3.0 datapack update after extracting it. |
| [Server datapack update](https://github.com/Dadcraft73/expedition-board/releases/download/v0.3.0/Expedition-Server-Update-0.3.0.zip) | Update an existing server while keeping its players and progress. |
| [Resource pack](https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.25/PLAY-Expedition-Coop-0.2.25.zip) | Underwater brightness/clarity, optional illustrated HUD and icons. The server can offer it automatically. |
| [Installation instructions](https://github.com/Dadcraft73/expedition-board/releases/download/v0.3.0/SERVER-INSTALL-0.3.0.txt) | A downloadable copy of the server setup guide. |

[View the release](https://github.com/Dadcraft73/expedition-board/releases/tag/v0.3.0). Choose the named downloads above; GitHub's **Source code** ZIP is not the playable world.

## Current playtest changes

Version 0.3.0 turns the tower into a staged siege with three working spawners, parkour and an armored upper keep. The enclosed arena has three waves and locks participants inside until victory or death. It also adds arrival lighting updates, single-panel flags, wider footprint surveys, cardinal headings, hours/minutes and a supplies pool instead of guaranteed trees. Start a new expedition match for the rebuilt encounters; an active older match keeps its mechanics and progress. Keep resource pack 0.2.25 and its SHA1 below. No Night Vision is added. If your server URL still says 0.2.12, its underwater/dark-area visibility improvements are not loaded: save the new URL/hash and confirm they persisted before restarting.

## One prepared region

After roughly ten seconds with players in an idle lobby, the game prepares one upcoming region: terrain around the five sites, structures, lighting and selected objectives. Chat announces when it is ready. Pressing Start reuses that region and card, loads the saved camp and runs the normal countdown. If you press Start early, the team waits in the lobby and starts automatically when preparation finishes.

Preparation never runs alongside an active match. A finished reserve survives reloads/restarts and releases its forced chunks; interrupted preparation cancels safely. After a match ends, the lobby prepares the next region. This prepares site terrain, **not every chunk of the 1024-block match box**. Exploring untouched terrain still generates chunks, and preparation can cause brief lobby lag. The larger encounters and footprint surveys increase preparation work. Starting an already prepared region still avoids building a new one at that moment; hosting performance varies.

## Install a fresh server

1. **Stop the server and back up its current world.**
2. Select **Vanilla Minecraft Java 26.3** and a compatible Java runtime. Local verification uses Java 25. Both players must also use Java Edition 26.3. No client mods, plugins, command blocks or RCON are required.
3. Upload and extract the 0.2.14 fresh server-world ZIP into the server's main folder, then extract the 0.2.25 datapack update inside its datapacks folder. You should have `expedition-coop/level.dat`, `expedition-coop/datapacks` and `expedition-coop/dimensions`. Avoid an extra nested `expedition-coop` folder.
4. Set the active world name to **`expedition-coop`** and spawn protection to **`0`**. Keep the host's assigned IP and ports. Use Survival, Normal difficulty, `force-gamemode=false` and `online-mode=true`. Whitelist your players for testing.
5. Configure the resource pack using the values below, save, and start the server.
6. Wait for the console's **Done** message, then join and accept the resource-pack prompt.

On Bisect, the main folder is normally `/home/container`. The world folder should be `/home/container/expedition-coop`. If a setting is absent from the panel, edit `server.properties` in the main folder while the server is stopped.

## Automatic resource-pack download

In **Settings → Server Properties**, paste only the value into each field:

| Field | Value |
|---|---|
| Resource Pack | `https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.25/PLAY-Expedition-Coop-0.2.25.zip` |
| Resource Pack SHA1 | `bdab8017f24ec8a2fd7800a4cc218baaec823787` |
| Require Resource Pack | `true` |
| Level Name / World Name | `expedition-coop` |
| Spawn Protection | `0` |

**Do not paste `resource-pack-sha1=` into the panel's SHA1 field.** That field takes only the 40-character value.

If editing the actual `server.properties` file instead, use these complete lines:

```properties
level-name=expedition-coop
spawn-protection=0
resource-pack=https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.25/PLAY-Expedition-Coop-0.2.25.zip
resource-pack-sha1=bdab8017f24ec8a2fd7800a4cc218baaec823787
require-resource-pack=true
```

Save and restart after changes. With the pack required, players must accept it to join. The cyan lobby download station is an optional manual fallback; it is unnecessary when automatic delivery succeeds.

For manual installation, download the resource-pack ZIP, keep it zipped, put it in your client's `resourcepacks` folder, and enable **Expedition Co-op 0.2.25** in Options → Resource Packs. Disable older Expedition/CTM packs. A server does not offer the world's embedded `resources.zip` automatically.

## Update an existing server

1. Stop the server and back it up.
2. Upload the **server datapack update ZIP** into `expedition-coop/datapacks`.
3. Extract it there, allowing overwrites. Confirm that the resulting file is `expedition-coop/datapacks/expedition-board/pack.mcmeta` and its description contains **0.2.25**.
4. **Move the update ZIP out of `datapacks` after extraction.** Keep the extracted `expedition-board` folder there.
5. Apply the resource-pack values above and restart.

This updates the datapack without replacing your world or player data. Existing compatible towers receive the targeted stair-clearance repair after loading. New runs use the updated vault with a tall magenta roof flag, matching banners and a lit entrance; an older run retains its existing vault.

## Start playing

1. Join the Expedition Hall. Everyone playing together selects the **same team color** at the wall panels beside the big board.
2. Check **TEAM STATUS**, then one player presses **START TEAM RUN**. That player becomes the run's host.
3. Wait for site generation and the countdown. Difficult terrain can take longer to prepare. Players arrive at the same camp.
4. Gather your own equipment. Right-click camp-board symbols for task details, or right-click the paper Challenge Card, open chat with **T**, and select a topic. An optional book is available there.

You share the timer, objective progress and banked relics. Supply goals combine **online teammates' inventories** and remove only the required total. For example, a six-porkchop goal can be completed with three cooked porkchops carried by each of two players. Extras remain yours. Only the selected collection requirement is banked; loose ingots and raw materials stay available for equipment.

### Current objectives

| Objective | What to do |
|---|---|
| Meals | A rotating cooked-meat or cooked-fish order, sometimes with multiple types. |
| Crafting | A selected iron/raw iron/copper/redstone block order, hopper or furnace minecart. |
| Harvest | Bread, baked potatoes, golden carrots, pumpkin pies or a mixed order. |
| Supplies | Eleven possible orders: navigation gear, rail supplies, lighting, glass, mechanisms, books, field equipment, pottery, an anvil, timber or boats. |
| Waystation | Repair its copper socket, fuel the barrel, light the fire, pull the lever and collect its relic. |
| Siege tower | Destroy three spawners, clear staged guards, complete the parkour plate and defeat the upper keep for the roof relic. |
| Buried vault | Find the magenta flag, descend through the entrance and solve the three-lamp circuit to open the relic chamber. |
| Sealed arena | Enter together, press the barrel button and survive three waves. The gates lock; death releases a player, all-party death resets, and victory opens the gates. |

Trees are two optional choices among eleven fourth-slot supplies orders. New matches do not install specimen groves. Older saved cards retain their selected requirements. Only complete orders bank; extras stay yours. The default HUD is a compact sidebar plus XYZ and cardinal heading; elapsed time uses hours/minutes. Toggle the larger illustrated HUD through the Challenge Card menu.

Either teammate may collect a relic. Banked progress survives death. Each player keeps their own equipment and bed spawn; the starting camp is the default respawn location. A newcomer can choose the active color to join at camp, while existing players cannot use team selection as a teleport.

During a run, the host can abandon through a separate confirmation, ending the whole team's expedition permanently. After all eight goals, fireworks celebrate your win in the Overworld. Either teammate may then return the team to the lobby through the chat link. The next run uses a fresh region in the same world.

## Troubleshooting

| Symptom | Check |
|---|---|
| Missing symbols or boxes in the HUD | Accept the server pack, or enable Expedition Co-op 0.2.25 manually and disable older packs. |
| Invalid SHA1 warning | The SHA1 field must contain only `bdab8017f24ec8a2fd7800a4cc218baaec823787`. |
| Missing metadata in `Expedition-Server-Update-0.3.0.zip` | Move that ZIP out of `datapacks`; leave its extracted `expedition-board` folder. |
| Normal terrain instead of the Expedition Hall | Check the active world name and folder nesting. |
| Lobby buttons cannot be used | Confirm spawn protection is `0` and restart. |
| `resource-pack-id missing, using default` | Minecraft supplied an ID; this message alone does not block startup. |
| The vault is hard to spot | In a new run, look for its tall magenta flag and matching entrance banners. Most rooms are underground. |

## Project status

This release is an eight-objective cooperative playtest. More objectives, difficulty options and further structure improvements are planned. Bedrock support is a future goal; this download is for Java Edition 26.3.

Inspired by Fetchr's replayable adventure format. Expedition Board is a separate project and is not an official Fetchr release.








