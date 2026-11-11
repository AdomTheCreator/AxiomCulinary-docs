# Ownership and region protection

Placed crops and stations belong to their placer. Normal use and removal require ownership or `axiomculinary.bypass`. A serving plate can allow public use when its station configuration has `public-use: true`; region permissions still apply.

## WorldGuard

WorldGuard support is included and optional. Install WorldGuard with its WorldEdit dependency, restart and check for the console message `Protezione WorldGuard attiva.`.

| Action | WorldGuard checks |
| --- | --- |
| Place | Build permission and block-place |
| Dismantle/break | Build permission and block-break |
| Use, collect, insert or serve | Container-style chest-access, plus interact denial |
| Area compost | Access at each affected crop |

An interaction-only allow flag does not automatically grant access to a station's contents. Configure public regions carefully because container flags also affect other blocks governed by WorldGuard.

`axiomculinary.bypass` bypasses internal ownership only. It does not bypass WorldGuard. WorldGuard's own session bypass is evaluated in the destination world, and it does not undo a denial from another claim adapter.

Changing a station's floor uses the ordinary block permissions for that floor. Crop support blocks remain protected until the crop is removed.

## Other claim plugins

Lands, GriefPrevention and similar systems do not have built-in adapters in this version. A server integration can handle `CulinaryAccessEvent` for USE, PLACE and REMOVE. Installing an arbitrary claim plugin does not by itself certify complete coverage of custom crop interactions.

If WorldGuard is installed but unavailable or its check fails, culinary access is denied rather than assumed safe. Correct the dependency or region problem and restart.

[Documentation home](Home.md)
