# Compatibility and verification

Documentation baseline: **0.13.0-SNAPSHOT**, verified on **11 November 2026**.

| Component | Verified combination |
| --- | --- |
| Server | Paper 26.3 build 242 |
| Java | Temurin 25.0.4.1 |
| Nexo | 1.29.1 |
| CraftEngine | Paper 26.9.2 beta |
| WorldGuard / WorldEdit | 7.0.21 / 7.4.6 |
| Network test clients | Protocol 26.1 through ViaVersion/ViaBackwards 5.12.2 |

These are tested combinations, not a claim that every version or server fork works. Folia support is not certified.

## Current checks

| Suite | Checks | Scope |
| --- | --- | --- |
| Unit tests | 41 | Rules, quality, timing, model choices, water charges and grouped-file validation |
| Configuration/server suite | 377 | Converted catalog, all items, 32 stations, 52 crop phases, wet soil, floors, all four games, profile snapshots and retired-component recovery |
| Fresh installation | 377 repeated checks | Same suite starting without old catalogs |
| Provider suite | 54 | Real Nexo/CraftEngine APIs, item identity, food, bottles, charges and mixed model stages |
| Connected-player suite | 104 | Real server players, menus, permissions, cooking, watering, floor replacement and new game clicks |

Fresh-install checks repeat the same scenarios and are not additional distinct cases. The provider test disables the providers at the end intentionally to verify unavailable-provider behavior.

## Boundaries

- Network clients are real connections without graphical rendering. Native 26.3 visuals with actual resource packs and shaders still need testing on the destination server.
- Native Nexo/CraftEngine furniture, arbitrary provider configurations and hot reloading those providers are not certified.
- The older full disk-failure regression suite was not rerun in full for the 0.12.0 configuration reorganization.
- Growth, cooking and aging advance in loaded chunks; there is no offline catch-up. Alcohol recovery uses real elapsed time.
- There are no certified large-farm or large-station performance figures. Test representative player counts and builds before a large rollout.
- Seasons, greenhouses, offline growth and crop-quality systems should not be inferred from earlier design ideas. They are not shipped features in this snapshot.

Public documentation does not include plugin binaries, implementation source or private test infrastructure.

[Documentation home](Home.md)
