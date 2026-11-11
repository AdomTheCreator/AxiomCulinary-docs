# Recipes and processing steps

Use `/culinary recipes [station]` for the current server catalog. Initial ingredients are inserted before starting. Ingredients requested during later steps are supplied when prompted; do not put all later additions into the initial slots.

## Step types

| Step | Interaction |
| --- | --- |
| MANUAL | Perform the requested number of actions with the named tool or an empty hand |
| INGREDIENT | Add the requested item at this point in the recipe |
| WAIT | Wait for loaded server time |
| HEAT | Provide heat for the requested duration |
| ATTEND | Heat and respond to stirring prompts |
| SERVE | Respond within the service window |
| TIMING | Click near the centre of the moving timing bar |

Missed prompts can reduce quality or burn a result, depending on the recipe. Empty-hand actions and tool actions are distinct. Tools used for a manual step are not consumed as ingredients.

The [recipe catalog](Recipe-Catalog.md) lists all default processing recipes. Crafting-table recipes are separate and can be viewed in the crafting menu.

## Add a small workflow recipe

The following is an additive example for a default installation with `baking_table` available. Save it as a **new** `content/food/demo.yml`, then run `/culinary reload`. The IDs are unique to this example.

```yaml
items:
  wiki_demo_salad:
    provider: vanilla
    material: BEETROOT_SOUP
    name: Garden salad
    nutrition: 4
    saturation: 0.6
    remainder: vanilla:BOWL
recipes:
  wiki_demo_salad_recipe:
    station: baking_table
    ingredients: [vanilla:CARROT, vanilla:BEETROOT]
    output: wiki_demo_salad
    amount: 1
    quality: true
    steps:
      - {action: MANUAL, item: knife, actions: 3}
      - {action: TIMING, actions: 2, seconds: 3}
```

Initial ingredients allow at most nine entries. Repeated entries require repeated units. Output quantity is 1–64. A workflow recipe needs a workflow station; a basic recipe without `steps` needs a legacy station. Do not create two recipes with the same initial ingredient multiset on the same station.

Active workflow batches retain a snapshot of their recipe. Changing a definition does not rewrite an existing batch. Empty stations before changing incompatible station modes or settings.

[Documentation home](Home.md)
