# Cooking quality

For the new rhythm, reaction and stirring games, see [Minigames](Minigames.md). All four games use the same quality tiers.

During a recipe-only TIMING step, right-click the **station** when the white cursor crosses the green centre. Usually use an empty main hand; a custom recipe can name a required tool. Do not click the floating text entity itself.

The default preset uses two rounds of three seconds. The first valid click in a round is the judgement for that round. Extra clicks do not improve it. A round that expires without a judgement scores zero. Wait for the next round after a judgement.

## Scores

| Average score | Quality | Bonus to base nutrition and saturation |
| --- | --- | --- |
| 0–54 | Common | None |
| 55–84 | Good | 10% |
| 85–100 | Excellent | 20% |

Nutrition is rounded up and capped at 20; saturation is also capped at 20. Scored ingredients can contribute to the new batch's average. Misses in supervised or service stages subtract from quality. Recipes without precision or scored ingredients retain their existing quality rules; burned food does not receive the precision bonus.

The timing bar normally appears above the station. With overhead status disabled, look at the station for action-bar feedback. The cursor updates every two ticks in loaded chunks; judgement follows server time, so latency and server lag affect perceived timing.

## Configure it

Edit the recipe in its station file; the old `cooking.yml` is archived after conversion.

```yaml
quality: true
steps:
  - {action: HEAT, seconds: 12}
  - {action: TIMING, actions: 2, seconds: 3}
  - {action: SERVE, seconds: 5}
```

This is a recipe fragment, not a complete content file. TIMING supports 1–200 configured actions and a 2–10 second cycle, with an optional `item`. A TIMING step does not itself add a heat requirement. HEAT and ATTEND do that.

The current quality and progress are saved with the batch. Normal unsaved tick progress can rewind after a crash, so retain coherent server backups.

[Documentation home](Home.md)
