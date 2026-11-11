# Default crop catalog

The default catalog contains 13 crops. These values come from a fresh **0.12.0-SNAPSHOT** installation. A server's configuration and in-game crop pages take precedence after customization.

| Crop ID | Seed | Harvest | Growth | Regrowth | Minimum light | Planting support |
| --- | --- | --- | --- | --- | --- | --- |
| `barley` | `barley_seeds` | `barley` ×3 | 500 s | 0 s | 8 | FARMLAND |
| `coffee` | `coffee_seeds` | `coffee_bean` ×3 | 600 s | 300 s | 8 | FARMLAND |
| `corn` | `corn_seeds` | `corn` ×2 | 600 s | 0 s | 8 | FARMLAND |
| `hops` | `hop_seeds` | `hops` ×3 | 500 s | 240 s | 8 | Below fence |
| `lettuce` | `lettuce_seeds` | `lettuce` ×2 | 400 s | 0 s | 8 | FARMLAND |
| `oat` | `oat_seeds` | `oat` ×3 | 500 s | 0 s | 8 | FARMLAND |
| `onion` | `onion_seeds` | `onion` ×2 | 480 s | 0 s | 8 | FARMLAND |
| `red_grape` | `red_grape_seeds` | `red_grapes` ×3 | 720 s | 300 s | 9 | Below fence |
| `rice` | `rice_seeds` | `rice` ×3 | 540 s | 0 s | 8 | FARMLAND |
| `strawberry` | `strawberry_seeds` | `strawberry` ×3 | 550 s | 240 s | 8 | FARMLAND |
| `tea` | `tea_seeds` | `tea_leaf` ×3 | 550 s | 250 s | 8 | FARMLAND |
| `tomato` | `tomato_seeds` | `tomato` ×3 | 600 s | 240 s | 8 | FARMLAND |
| `white_grape` | `white_grape_seeds` | `white_grapes` ×3 | 720 s | 300 s | 9 | Below fence |

Times are loaded server seconds, not offline time. A regrowth value greater than zero keeps the plant and resets part of its progress after harvesting. With zero regrowth, harvesting removes the plant and returns its seed. Moisture, light and support requirements still apply.

Each crop file is in `content/crops/<id>.yml`. It includes its growth rules and its model choices per stage. Some item definitions are shared between crops and appear only once; keep those references valid when reorganizing files.

[Documentation home](Home.md)
