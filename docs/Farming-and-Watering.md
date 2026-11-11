# Farming and watering

## Planting and growth

Most crops are planted by right-clicking the top of farmland. Grapes and hops hang below an overhead fence: click its bottom face with the corresponding seed. The crop's configuration defines its support materials, light requirement, growth duration, yield and regrowth time.

Crops have no solid collision. Use the custom plant interaction, not a vanilla berry-bush placement. Looking at your own crop shows growth and water status when crop feedback is enabled.

## Moist farmland

Ground-planted crops read the moisture of the farmland directly below them. When that soil is wet, crop moisture stays at 100 and a watering attempt spends no charges. Nearby source water can hydrate that soil through Minecraft's normal farmland rules.

When the soil is dry, stored crop moisture can still support growth until it runs out. Moisture normally decreases by one point every ten loaded seconds when no automatic watering applies. A dry crop with no stored moisture stops growing. Rain in a suitable biome under open sky and active sprinklers can also water crops.

Hanging crops need their configured support and their own water supply through watering, rain or sprinklers; the ground-planted farmland rule does not automatically irrigate a fence.

## Watering cans

1. Hold **one** can in your main hand.
2. Right-click source water to refill it. Flowing water does not refill it; the source is not removed.
3. Right-click a crop to restore its moisture to 100.

New cans start empty and are unstackable. The default holds 16 units and costs one unit per watering. The description shows its remaining water. Creative mode does not spend charges. A refused action, fully watered crop or already-wet farmland does not spend water.

Old cans without charge data start with one full tank when first used. Split any old stacks before use. Custom cans can define `watering-can.capacity` and `watering-can.per-use` under their item in `content/tools/tools.yml`; both must be positive integers, the cost cannot exceed capacity, and capacity is capped at 10000.

## Fertilizer and sprinklers

Bone meal and the basic compost add 15% of the crop's total growth duration, up to maturity. Survival uses one item; creative mode and an already-mature plant do not consume it. Area compost applies to authorized crops in its area.

The sprinkler remains available. Fill it with a water bucket. By default it pulses every ten loaded seconds, spends one stored charge and covers a square of radius four within one block vertically. Its radius and capacity are set in `content/farming.yml`.

Water pumps, irrigation pipes and water tanks were removed in 0.12.0. Existing placed components are inactive recovery markers; see [Updates and backups](Updates-and-Backups.md).

[Documentation home](Home.md)
