# Configuration layout and examples

All paths below are inside `plugins/AxiomCulinary/`.

```text
config.yml
content/
  stations/<id>.yml
  crops/<id>.yml
  food/food.yml
  drinks/alcohol.yml
  drinks/juices.yml
  drinks/other.yml
  drinks/settings.yml
  ingredients/ingredients.yml
  tools/tools.yml
  farming.yml
world.yml
legacy-config/
```

Some optional groups are absent when empty. `config.yml` controls the message tag, colours, work-item scale, overhead status and particles. `world.yml` stores placed objects, ownership and progress; it is not a content catalog.

The loader reads every `.yml` below `content/`. File order does not resolve duplicate definitions: duplicates are rejected even if they contain different fields. Move an entry when reorganizing; do not copy it into a second active file. Keep backups outside `content/`. Symbolic links are not supported there.

## A station in one file

For example, `content/stations/camp_grill.yml` holds four related sections:

| Section | Purpose |
| --- | --- |
| `items.camp_grill` | Inventory item, name, lore and provider |
| `stations.camp_grill` | Interaction block, mode, slots, fuel and crafting material |
| `recipes` | Recipes processed by this station |
| `models.stations.camp_grill` | Placed model, scale, offset and work surface |

Edit an existing file instead of adding a duplicate station definition. Inventory appearance and placed-model appearance are independent choices in that same file.

## A crop in one file

`content/crops/tomato.yml` contains `crops.tomato`, its local item definitions and `models.crops.tomato.stages`.

Important crop fields are `seed`, `harvest`, fallback item `stages`, `grow-seconds`, `yield`, `regrow-seconds`, `supports`, `support-face` and `min-light`. Model stages are separate from fallback item IDs. Shared items are defined only once and referenced by other crops.

## Messages and feedback

Edit these values inside the existing `config.yml`:

```yaml
messages:
  tag: '[AxiomCulinary]'
  colors:
    info: '#D3D3D3'
    success: '#55FF55'
    error: '#FF5555'
visuals:
  work-item-scale: 0.3
  work-item-gap: 0.025
  station-status: true
  crop-status: true
  status-height: 1.45
  processing-particles: true
```

The tag is plain text and always white. Colours use six-digit hex strings. Model choices belong to the station/crop files, not this global visual-feedback section.

## Reload safely

Use `/culinary reload` after saving. Syntax errors, duplicate IDs, missing references and invalid model choices reject the new snapshot; the active catalog and presentation remain unchanged. Successful reloads close open menus.

Do not remove definitions still placed in the world. Empty stations before changing incompatible settings or aging mode. IDs use lowercase letters, digits, underscores and hyphens.

`enabled: false` disables a whole content file, but all remaining references still have to be valid. The built-in `knife`, `watering_can`, `fertilizer` and `sprinkler` item IDs are required. Keep required default items unless you also understand the plugin's built-in crafting dependencies.

For examples of complete additive content, see [Recipes](Recipes.md). For visual choices, see [Models and providers](Models-and-Providers.md). For conversion of older files, see [Updates and backups](Updates-and-Backups.md).

[Documentation home](Home.md)
