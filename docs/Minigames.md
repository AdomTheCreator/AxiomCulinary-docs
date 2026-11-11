# Cooking minigames

AxiomCulinary 0.13.0 provides **timing, rhythm, reaction and balance/stirring** games. Configure difficulty in `plugins/AxiomCulinary/minigames.yml`, then select a profile in the station's own file.

## Choose the game for a station

Edit the existing definition in `content/stations/baking_table.yml`:

```yaml
stations:
  baking_table:
    minigame: rhythm_normal
```

Keep the other station fields. Do not put a duplicate station ID in a second file. Empty its ingredients and batches before changing the selection, then use `/culinary reload`.

The selected profile replaces interactive TIMING/MINIGAME phases in that station's recipes. A recipe without one gains a game phase before final service, or after its other work. Basic legacy recipes are wrapped as workflows in memory, preserving their original cutting, waiting or heating step. Quality is enabled for the resulting preparations.

Without a selection, or with `minigame: recipe`, recipes retain their original behavior. Existing timing rounds keep their original duration and scoring. Aging racks, serving plates and stations without processing recipes cannot select a game profile.

## How to play

Right-click the station, not its floating text. Normally use an empty main hand; a phase that requires a tool tells you which one.

| Game | Goal |
| --- | --- |
| `timing` | Click when the moving cursor reaches the green centre |
| `rhythm` | Follow the repeating beat and click around each signal |
| `reaction` | Wait for a randomized signal, then respond quickly; an early click scores zero |
| `balance` | Click to raise the bar and keep it inside the green band as it falls |

Timing, rhythm and reaction accept one judgement per round. The first click counts; extra clicks do not improve it. An unattended round scores zero. Reaction chooses a new signal time each round and keeps that time in the saved batch. Its first part of the response window gives full points; the score then decreases to zero.

Balance scores control throughout the round. Clicking raises the level rather than directly earning points. Letting the bar empty or spamming it to the top gives poor results. Stay inside the band for a high score.

For parallel batches, configured game phases queue one at a time. Waiting batches do not lose game time or quality; the other recipe work continues. Existing recipe-only timing behavior is retained for older unselected stations.

Overhead text shows the game, its progress and current instructions. When overhead status is disabled, look at the station for action-bar feedback. Timing and balance use a bar; rhythm and reaction show a clear signal and play a sound.

## Difficulty profiles

There are twelve defaults: four games, each with `_easy`, `_normal` and `_hard`. The suffix is a readable profile name; its numeric settings determine difficulty. You can add your own profile ID and select it on any compatible station.

Edit existing entries under `profiles` in `minigames.yml`:

```yaml
profiles:
  rhythm_normal:
    game: rhythm
    rounds: 4
    seconds: 2
    window-ticks: 6
    cooldown-ticks: 4
  reaction_normal:
    game: reaction
    rounds: 3
    seconds: 3
    window-ticks: 14
  balance_normal:
    game: balance
    rounds: 1
    seconds: 8
    lower: 40
    upper: 60
    decay-per-second: 15
    click-boost: 12
```

| Setting | Meaning |
| --- | --- |
| `game` | timing, rhythm, reaction or balance |
| `rounds` | 1–20 rounds |
| `seconds` | 2–10 seconds per round |
| `window-ticks` | Scoring tolerance or reaction response window; from 2 ticks to half the round |
| `cooldown-ticks` | Minimum click interval, 4–20 ticks; default 4 |
| `lower`, `upper` | Balance band, within 10–90 and at least 10 units wide |
| `decay-per-second` | Balance level lost per second, 1–50 |
| `click-boost` | Balance increase per accepted click, 1–30 |

At normal server speed, 20 ticks are one second. Wider windows and wider balance bands make a game more forgiving. Balance decay and click boost should be adjusted together. A profile file can contain up to 128 profiles; unknown fields and invalid values reject reload.

## Quality, saves and reload

All games feed the same food-quality score: Common at 0–54, Good at 55–84 and Excellent at 85–100, with the existing 0%, 10% and 20% bonuses. Ingredient scores and mistakes in other recipe phases still contribute.

A batch stores its effective profile, progress, randomized signal, balance level and score. Changing a global profile affects new batches without rewriting games already underway. Invalid profiles preserve the active catalog and presentation. Changing the station's profile while it contains work is refused until it is emptied.

Accepted clicks use the normal transactional save path. Automatic clock progress uses periodic saving and can rewind after a crash. Older plugin versions cannot read new MINIGAME snapshots; restore a coherent backup for a downgrade.

Latency and server lag affect perceived timing. The hardest profiles are not a promise of balanced difficulty for every player or network; tune them on your server.

[Documentation home](Home.md)
