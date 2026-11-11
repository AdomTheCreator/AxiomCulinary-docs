# Food, wine and other drinks

Prepared meals use native food properties and may return a configured container. Drinks use a native drinking animation, can be consumed at full hunger and normally return a glass bottle. A custom `remainder` can replace the container.

## From grapes to wine

1. Plant red or white grape seeds under an appropriate overhead fence. Keep the vine supported, lit and watered.
2. At `grape_press`, insert three matching grapes and one empty glass bottle. Start with an empty hand and perform the six requested presses.
3. Ferment the resulting juice with sugar at `fermenter`. The default red and white wine recipes take 180 loaded seconds. Berry wine uses an additional berry ingredient and a different duration.
4. Put an ageable bottle in `wine_rack` to mature. The rack holds one bottle. Collect it with an empty hand; moving or reinserting it preserves accumulated age.

The default rack gains one age second per loaded second, multiplied by 1.5 when it has no sky light. Red and white wine reach higher tiers at 600-second intervals, up to tier three. Other drinks can have different thresholds. Age increases the configured effect within its limits.

Apple pressing, cider, mead, brewing, distilled spirits, cocktails, non-alcoholic mixes, teas and coffee use their own station recipes. The apple press includes timing steps in a fresh installation. Fermentation does not need fire; distillation and hot brewing may require heat. Read the current recipe rather than adding another bottle automatically.

## Alcohol status

Alcohol adds a **gameplay score from 0 to 100**, not a real-world blood-alcohol measure. By default it decreases by one point every 15 real seconds, including offline time. Nausea starts at 40 and slowness at 70. Use `/culinary alcohol` to inspect your status.

Juices can use `drink.alcohol: 0`. The alcohol score, symptoms, aging multiplier and item effects are configurable.

## Files

| Path under content/ | Contents |
| --- | --- |
| `food/food.yml` | Prepared food definitions |
| `drinks/alcohol.yml` | Wine, beer and other alcoholic drinks |
| `drinks/juices.yml` | Juices |
| `drinks/other.yml` | Other drinks, when present |
| `drinks/settings.yml` | Global alcohol and cellar settings |
| `stations/<id>.yml` | The relevant processing recipes |

You can split the item groups into smaller files while preserving unique IDs. Some edible harvests are defined in their crop file rather than the prepared-food group.

[Documentation home](Home.md)
