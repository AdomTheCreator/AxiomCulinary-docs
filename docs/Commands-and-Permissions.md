# Commands and permissions

The main command is `/culinary`. Aliases are `/ac` and `/axiomculinary`.

| Command | Purpose | Permission |
| --- | --- | --- |
| `/culinary` or `/culinary help` | Open the main menu | `axiomculinary.use` |
| `/culinary recipes [station]` | Browse processing recipes | `axiomculinary.use` |
| `/culinary items` | Open the item catalog | `axiomculinary.use` |
| `/culinary alcohol` | View personal alcohol status | `axiomculinary.use` |
| `/culinary give <player> <item> [1-64]` | Give a catalog item to an online player | `axiomculinary.admin` |
| `/culinary reload` | Validate and reload configuration | `axiomculinary.admin` |

Use catalog IDs such as `watering_can`, `cutting_board` or `tomato_seeds`. Menus show the active IDs. The console uses text output for supported command views; player menus require a player.

## Permission reference

| Permission | Default | Effect |
| --- | --- | --- |
| `axiomculinary.use` | Everyone | Menus and normal interactions |
| `axiomculinary.admin` | Operators | Give/reload; includes global catalog withdrawal |
| `axiomculinary.catalog.take` | Operators | Withdraw any catalog item |
| `axiomculinary.catalog.take.<category>` | Nobody | Withdraw only that category |
| `axiomculinary.bypass` | Operators | Bypass AxiomCulinary ownership checks |

Category suffixes are `stations`, `tools`, `seeds`, `crops`, `ingredients`, `food`, `drinks` and `other`. Browsing does not require withdrawal permission. These permissions do not bypass WorldGuard or other claim adapters.

## LuckPerms examples

These are permission assignments to run through LuckPerms, if you use it. Replace the example group with one you manage.

```text
lp group chef permission set axiomculinary.catalog.take.food true
lp group chef permission set axiomculinary.catalog.take.drinks true
lp group culinaryadmin permission set axiomculinary.admin true
```

For a normal survival group, leave catalog withdrawal ungranted. Giving only category withdrawal does not grant the administrative `give` or `reload` commands.

[Documentation home](Home.md)
