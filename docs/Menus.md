# Menus and catalog

`/culinary` opens the inventory menu. It provides stations, processing recipes, items, registered crafting recipes, crops, help and alcohol status. Lists show up to 36 entries per page, with navigation along the bottom.

## Find an item or recipe

- Open a station to read its uses and related recipes.
- Open a recipe to inspect the initial ingredient slots, result amount and processing steps. Repeated icons mean repeated units.
- Open the item catalog to filter by category. Left-click opens details; right-click requests one item if you have withdrawal permission.
- The crafting view shows recipes actually registered by AxiomCulinary. External-provider crafting recipes must be managed through that provider.

Opening a guide does not insert ingredients, consume items or start a batch. Work happens at the physical station.

## Withdraw items

Use right-click in the catalog list or the one-item delivery button in its detail page. The action checks your current global or category permission. If your inventory is full, excess delivery drops on the ground.

Preview icons cannot be taken through inventory tricks. Shift-click, number keys, dragging, dropping and similar transfers are blocked while the menu is open; close it before arranging your inventory.

A successful reload closes menus so they cannot act on an old catalog. A rejected reload retains the active catalog. Revoked permissions are checked again when you request delivery.

There is no configuration editor or text-search field in these menus. Edit the grouped YAML files for configuration changes.

[Documentation home](Home.md)
