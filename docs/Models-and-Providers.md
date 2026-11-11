# Models and item providers

The default models for 32 stations and 13 crops are built into the plugin. Their geometry is not an editable list of parts. The old `models.yml` and `crop-models.yml` do not override it.

## Inventory items

Each item can use one of these providers:

| Provider | Required fields | Purpose |
| --- | --- | --- |
| `vanilla` | `material` | A Minecraft item |
| `head` | `base64` | A player head with an encoded texture profile |
| `nexo` | `id` | An item already registered by Nexo |
| `craftengine` | `id` | An item already registered by CraftEngine |

For example, edit an existing station's inventory item:

```yaml
items:
  camp_grill:
    provider: nexo
    id: culinary_grill
    name: Camping grill
```

Replace the example external ID with one installed on your server. Do not paste this into another file if `camp_grill` is already defined. Base64 requires an actual encoded profile containing a valid Minecraft texture URL; arbitrary text is not a texture profile.

Original Nexo/CraftEngine items are recognized through their provider identity, not merely by their vanilla material. Missing provider items are not silently replaced by unrelated vanilla items. Configure external-provider survival crafting in that provider; built-in crafting for an external result is omitted.

## Placed station model

In the same station file:

```yaml
models:
  stations:
    camp_grill:
      provider: base
      scale: {x: 1, y: 1, z: 1}
      offset: {x: 0, y: 0, z: 0}
      surface: 0.85
```

`base` uses the built-in model and takes no external ID. For Nexo or CraftEngine, change the provider and add `id`. These are rendered item models attached to AxiomCulinary mechanics; native provider furniture placement is not promised.

The optional `surface` sets the work-item height. Scale per axis is 0.05–4; offsets are -2–2; a custom work surface is 0.01–4. The station's interaction block and the floor below are separate from its visual model.

## Crop model per growth stage

Edit the model section in the crop's own file:

```yaml
models:
  crops:
    tomato:
      stages:
        - {provider: base, scale: 1}
        - {provider: nexo, id: tomato_young, scale: 0.8}
        - {provider: craftengine, id: 'farm:tomato_flowering', scale: 1}
        - {provider: nexo, id: tomato_ripe, scale: 1}
```

Each stage has its own provider, size and offset. There can be 1–8 visual stages; the last represents maturity. With four stages, thresholds are 0%, one third, two thirds and 100%. The built-in stages already have growing shapes, so scale 1 keeps their intended dimensions.

Without an explicit model profile, default vanilla content uses its internal model when available; external catalog items retain their item-based appearance. Explicit profiles override that visual choice without changing harvests, recipe identity or containers.

Reload validates external model IDs immediately. Startup briefly waits for provider catalogs; a persistently unavailable model stops loading while preserving saved world data. The [compatibility page](Compatibility.md) distinguishes API checks from actual resource-pack rendering tests.

[Documentation home](Home.md)
