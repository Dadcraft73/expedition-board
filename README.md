# Expedition Board

A replayable Minecraft adventure from Dadcraft73. Gather supplies, grow a tree, explore biome-themed encounters and bank relics together.

**Current playtest: 0.2.18 · Minecraft Java Edition 26.3 · eight objectives.** Play solo or as one cooperative team. One expedition runs at a time; the four selectable colors do not create simultaneous competing matches. This is a work in progress, and human testing is still assessing pacing, combat and structures.

## Downloads

| Download | Use it for |
|---|---|
| [Fresh server world](https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.14/Expedition-Coop-Server-0.2.14.zip) | Base world for a new installation. Apply the 0.2.18 datapack update after extracting it. |
| [Server datapack update](https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.18/Expedition-Server-Update-0.2.18.zip) | Update an existing server while keeping its players and progress. |
| [Resource pack](https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.18/PLAY-Expedition-Coop-0.2.18.zip) | Underwater brightness/clarity, optional illustrated HUD and icons. The server can offer it automatically. |
| [Installation instructions](https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.18/SERVER-INSTALL-0.2.18.txt) | A downloadable copy of the server setup guide. |

[View the release](https://github.com/Dadcraft73/expedition-board/releases/tag/v0.2.18). Choose the named downloads above; GitHub's **Source code** ZIP is not the playable world.

## Underwater visibility and recent updates

Version 0.2.18 requires BOTH the datapack update and the new resource pack. It improves underwater fog and lifts dark underwater colors without night vision. Land lighting stays as before. The pack also includes the compact default HUD, rotating collection tasks, tougher encounters, fewer signs and staged terrain preparation. Keep the normal watchdog enabled.

## Install a fresh server

1. **Stop the server and back up its current world.**
2. Select **Vanilla Minecraft Java 26.3** and a compatible Java runtime. Local verification uses Java 25. Both players must also use Java Edition 26.3. No client mods, plugins, command blocks or RCON are required.
3. Upload and extract the 0.2.14 fresh server-world ZIP into the server's main folder, then extract the 0.2.18 datapack update inside its datapacks folder. You should have `expedition-coop/level.dat`, `expedition-coop/datapacks` and `expedition-coop/dimensions`. Avoid an extra nested `expedition-coop` folder.
4. Set the active world name to **`expedition-coop`** and spawn protection to **`0`**. Keep the host's assigned IP and ports. Use Survival, Normal difficulty, `force-gamemode=false` and `online-mode=true`. Whitelist your players for testing.
5. Configure the resource pack using the values below, save, and start the server.
6. Wait for the console's **Done** message, then join and accept the resource-pack prompt.

On Bisect, the main folder is normally `/home/container`. The world folder should be `/home/container/expedition-coop`. If a setting is absent from the panel, edit `server.properties` in the main folder while the server is stopped.

## Automatic resource-pack download

In **Settings → Server Properties**, paste only the value into each field:

| Field | Value |
|---|---|
| Resource Pack | `https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.18/PLAY-Expedition-Coop-0.2.18.zip` |
| Resource Pack SHA1 | `b4ff21a24205858196e51528f1a010970430bb85` |
| Require Resource Pack | `true` |
| Level Name / World Name | `expedition-coop` |
| Spawn Protection | `0` |

**Do not paste `resource-pack-sha1=` into the panel's SHA1 field.** That field takes only the 40-character value.

If editing the actual `server.properties` file instead, use these complete lines:

```properties
level-name=expedition-coop
spawn-protection=0
resource-pack=https://github.com/Dadcraft73/expedition-board/releases/download/v0.2.18/PLAY-Expedition-Coop-0.2.18.zip
resource-pack-sha1=b4ff21a24205858196e51528f1a010970430bb85
require-resource-pack=true
```

Save and restart after changes. With the pack required, players must accept it to join. The cyan lobby download station is an optional manual fallback; it is unnecessary when automatic delivery succeeds.

For manual installation, download the resource-pack ZIP, keep it zipped, put it in your client's `resourcepacks` folder, and enable **Expedition Co-op 0.2.18** in Options → Resource Packs. Disable older Expedition/CTM packs. A server does not offer the world's embedded `resources.zip` automatically.

## Update an existing server

1. Stop the server and back it up.
2. Upload the **server datapack update ZIP** into `expedition-coop/datapacks`.
3. Extract it there, allowing overwrites. Confirm that the resulting file is `expedition-coop/datapacks/expedition-board/pack.mcmeta` and its description contains **0.2.18**.
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
| Trees | Leaves, logs, stripped logs, bark-covered wood, stripped wood or boats from five required species. |
| Waystation | Repair its copper socket, fuel the barrel, light the fire, pull the lever and collect its relic. |
| Watchtower | Defeat both guards, climb the stairs and collect the unlocked rooftop relic. |
| Buried vault | Find the magenta flag, descend through the entrance and solve the three-lamp circuit to open the relic chamber. |
| Fortified camp | Activate the encounter, defeat both mixed-mob waves and collect the relic. |

The tree pool uses oak, birch, spruce, acacia and cherry. Specimen groves guarantee all five. Your selected recipe determines the required items and counts; logs and bark-covered wood are different items. The default HUD is a compact sidebar plus XYZ text. Toggle the larger illustrated HUD through the Challenge Card menu.

Either teammate may collect a relic. Banked progress survives death. Each player keeps their own equipment and bed spawn; the starting camp is the default respawn location. A newcomer can choose the active color to join at camp, while existing players cannot use team selection as a teleport.

During a run, the host can abandon through a separate confirmation, ending the whole team's expedition permanently. After all eight goals, fireworks celebrate your win in the Overworld. Either teammate may then return the team to the lobby through the chat link. The next run uses a fresh region in the same world.

## Troubleshooting

| Symptom | Check |
|---|---|
| Missing symbols or boxes in the HUD | Accept the server pack, or enable Expedition Co-op 0.2.18 manually and disable older packs. |
| Invalid SHA1 warning | The SHA1 field must contain only `b4ff21a24205858196e51528f1a010970430bb85`. |
| Missing metadata in `Expedition-Server-Update-0.2.18.zip` | Move that ZIP out of `datapacks`; leave its extracted `expedition-board` folder. |
| Normal terrain instead of the Expedition Hall | Check the active world name and folder nesting. |
| Lobby buttons cannot be used | Confirm spawn protection is `0` and restart. |
| `resource-pack-id missing, using default` | Minecraft supplied an ID; this message alone does not block startup. |
| The vault is hard to spot | In a new run, look for its tall magenta flag and matching entrance banners. Most rooms are underground. |

## Project status

This release is an eight-objective cooperative playtest. More objectives, difficulty options and further structure improvements are planned. Bedrock support is a future goal; this download is for Java Edition 26.3.

Inspired by Fetchr's replayable adventure format. Expedition Board is a separate project and is not an official Fetchr release.



