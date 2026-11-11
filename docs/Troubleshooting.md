# Troubleshooting

## The plugin does not enable

Confirm Java 25 and the Paper version, remove duplicate JARs and read the **first AxiomCulinary error** in the startup log. Invalid content, unavailable model providers and invalid saved state can stop startup to preserve data. Keep a copy of the configuration before changing it.

## Reload is refused

Check indentation, duplicate IDs and references between files. An entry cannot be spread across two files with the same ID. Make sure a station or crop still placed in the world keeps its definition. Empty stations before changing incompatible modes or settings.

Backups ending in `.yml` inside `content/` are loaded too. Move them outside that folder. Changes to archived `legacy-config/` files do not change the active catalog.

## I cannot plant or harvest

Use the right seed, support material and face. Ground crops use the top of farmland; grapes and hops use the bottom of an overhead fence. Check ownership and region permissions. Vanilla fruit items do not automatically become plugin seeds.

If growth stops, inspect moisture, light, support and whether the chunk is loaded. Fertilizer only helps an immature plant. Hanging plants do not receive automatic farmland hydration merely because a fence is nearby.

## My watering can does nothing

New cans start empty. Hold one in the main hand and aim at source water to refill; flowing water and solid obstructions do not work. Separate old stacked cans. A fully watered crop or wet farmland does not spend a charge. A region denial can block the source or the crop separately.

## A station stops processing

Read the current step: it may need a tool, a later ingredient, water, fuel, stirring, timing or collection. Heat-dependent work pauses when the source is removed or unlit. A floor replacement does not itself delete a batch.

Use an empty main hand for the usual start/collect interactions. During TIMING, click the station rather than its floating text. One judgement counts per round.

## A custom model is missing

Check the `models` section in the station or crop file, including provider and external ID. The inventory item's provider is a separate setting. Install the provider and its correct pack, check scale/offset and reload. A catalog preview barrier explains an unavailable item; it is not an actual replacement model.

## I can browse but cannot take items

Browsing and withdrawal have different permissions. Grant the global catalog permission or the appropriate category permission only if players should receive free items. Inventory menus deliberately block moving their preview icons.

## Storage failure or interrupted conversion

Resolve the reported file permission, disk or provider problem and restart. Preserve `world.yml`, player data, `content/`, `legacy-config/` and any remaining `content-migration/` until the problem is understood. Do not erase state as a first troubleshooting step.

## Report a problem

Include the plugin version, Java version, exact server build, relevant optional-plugin versions, steps to reproduce and the first relevant error. Share only a minimal configuration example; remove credentials, tokens, private endpoints, player identifiers and other private information before posting an issue.

[Documentation home](Home.md)
