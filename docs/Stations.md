# Stations and physical cooking

Place a station item, insert the initial ingredients with right-clicks and follow its instructions. Most stations start with an empty-hand right-click. The camp grill starts individual batches and can hold four at once.

## Default stations

| Station ID | Purpose | Mode | Slots |
| --- | --- | --- | --- |
| `apple_press` | Apple mash and juice | workflow | 1 |
| `baking_table` | Dough, rolling, fillings and cutting | workflow | 1 |
| `brew_kettle` | Brewing grain-based drinks | workflow | 1 |
| `camp_grill` | Four independent grill batches | workflow | 4 |
| `chef_pot` | Meals with staged additions | workflow | 1 |
| `cocktail_bar` | Cocktails and mixed drinks | workflow | 1 |
| `composter` | Area compost production | workflow | 1 |
| `culinary_stove` | Fuelled heat source for the station above | workflow | 1 |
| `cutting_board` | Knife-based ingredient preparation | legacy | 1 |
| `distiller` | Distilled drinks; requires heat | legacy | 1 |
| `fermenter` | Wine, cider, mead and beer fermentation | legacy | 1 |
| `freezer` | Ice and frozen ingredients | workflow | 1 |
| `grape_press` | Press red or white grape juice | legacy | 1 |
| `herbal_cauldron` | Herbal and potion combinations | workflow | 1 |
| `jam_pot` | Jam with supervised cooking | workflow | 1 |
| `marshmallow_roaster` | Timed roasting and service | workflow | 1 |
| `mincer` | Manual mincing | workflow | 1 |
| `mixer` | Basic mixing and dough | legacy | 1 |
| `mixing_bowl` | Ordered ingredient assembly | workflow | 1 |
| `oven` | Baking with heat | legacy | 1 |
| `pan` | Pan cooking with heat | legacy | 1 |
| `pot` | Basic cooking with heat | legacy | 1 |
| `prairie_bowl` | Stew assembled in stages | workflow | 1 |
| `roaster` | Roasting and ingredient effects | workflow | 1 |
| `serving_plate` | Up to four matching food portions | plate | 1 |
| `silo` | Dry ingredients | workflow | 1 |
| `smoking_station` | Wood-flavoured smoking | workflow | 1 |
| `steamer` | Steamed food | workflow | 1 |
| `tea_kettle` | Tea, coffee and hot drinks | workflow | 1 |
| `wind_mill` | Weather-sensitive milling | workflow | 1 |
| `wine_rack` | One-bottle aging | legacy | 1 |
| `wok` | Staged stir-fry cooking and service | workflow | 1 |

The mode describes how the station works: `legacy` uses basic recipes, `workflow` uses explicit steps, and `plate` serves food. Empty slots do not imply every recipe can run on every station.

## Heat and fuel

Cooking steps that need heat pause without it. Supported sources directly below include magma, lava, fire, soul fire and lit campfires, furnaces, smokers or blast furnaces. A fuelled culinary stove can heat the station above it. Some stations also accept configured internal fuel.

The menu only shows heat requirements where relevant. Pressing, fermentation and waiting do not inherently need a fire. Removing a heat source pauses heat-dependent work instead of deleting the batch.

## Ingredients and recovery

Inserted ingredients appear on the work surface. Sneak + empty-hand right-click can recover the last unstarted ingredient or cancel the last workflow batch. A running batch returns its inputs; a completed one returns its output and applicable containers. Spent water and fuel are not refunded.

Sneak + empty-hand left-click dismantles a station you are allowed to remove. Finished results and unfinished inputs are handled according to the batch state rather than being duplicated.

## Replacing the floor

Break and replace the block **below** a station as you would any other floor. You do not need to remove the station, and its contents remain. Terrain protection still applies. The station's own interaction block cannot be replaced by a native block placement.

Crop support blocks are different: remove the crop before breaking its farmland or supporting fence.

## Select a minigame

Set `stations.<id>.minigame` to a profile such as `rhythm_normal`, `reaction_easy` or `balance_hard`. Profiles are configured in `minigames.yml`. The game is shown in the station menu and its effective recipe steps. See [Minigames](Minigames.md).

## Configure a station

`content/stations/<id>.yml` contains its inventory item, station settings, processing recipes and placed model. The `block` field is the station's own interaction block, usually `BARRIER`; it is not the floor below it. See [Configuration](Configuration.md) and [Models and providers](Models-and-Providers.md).

[Documentation home](Home.md)
