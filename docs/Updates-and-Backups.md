# Updates and backups

## Update from 0.12 to 0.13

After a normal stopped-server JAR update, `minigames.yml` is created if missing. Existing station files are not overwritten. With no minigame selection, existing recipes keep their previous behavior. Select a profile per station to enable the new games. Effective profiles are stored with new batches, and older versions cannot read new MINIGAME snapshots: keep a coherent backup for rollback.

## First conversion introduced in 0.12.0

1. Stop the server.
2. Back up the **whole world/player data and the complete AxiomCulinary folder together**.
3. Replace the old plugin JAR, leaving only one AxiomCulinary JAR installed.
4. Start the server and inspect the conversion result before opening normal play.
5. Edit the new `content/` files for future changes.

The first 0.12.0 startup imports the previous flat catalogs, preserves their enabled content and customizations, applies applicable cooking presets, validates the result and activates the grouped folder. The five old configuration files are backed up in `legacy-config/`; originals matching the saved copy are removed from their old location.

| Previous file | New location |
| --- | --- |
| `content.yml` | Crop, station, item and farming groups |
| `vinery.yml` | Crop/station groups and drinks/settings files |
| `mechanics.yml` | Crop, station, food, ingredient and tool groups |
| `cooking.yml` | Explicit recipe steps and station fuel settings |
| `visuals.yml` | Model sections in the respective station/crop files |

`config.yml` remains the general configuration. `world.yml` retains placed objects and progress. Old geometric `models.yml` and `crop-models.yml` are not imported as editable geometry.

## Removed water-network components

Pump, irrigation-pipe and water-tank items, stations and crafting entries are removed from the active catalog. Old placed components remain as inactive, visible recovery markers. Their owner can sneak + empty-hand left-click to dismantle them, recovering a piston, copper grate or glass and any stored item contents.

Removed definitions are retained in `legacy-config/removed-water-network.yml`. Existing inventory copies are not automatically deleted or turned into new active stations. Sprinklers remain supported.

## Back up after conversion

Treat `content/` as your customized source from now on. Do not delete it to regenerate defaults: old flat files are no longer the active catalog. Keep coherent backups of configuration, `world.yml`, worlds and player inventories.

If `content-migration/` remains after a failed conversion, preserve it and inspect the log. Do not delete the only copy of customized data to force a retry. Existing backup files are not overwritten.

A failed reload retains the running snapshot. A storage failure stops the plugin to avoid continuing with unsaved state; resolve the file/disk problem and restart. Restoring only the JAR does not roll back world or inventory data. Downgrades require restoring a compatible backup, not reusing newer batch state blindly.

[Documentation home](Home.md)
