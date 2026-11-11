# Installation

## Requirements

| Component | Requirement |
| --- | --- |
| Server | Paper 26.3; build 242 is the verified build |
| Java | Java 25 |
| Client | A compatible Minecraft Java client |
| Optional content providers | Nexo or CraftEngine |
| Optional region protection | WorldGuard, with its WorldEdit dependency |

The default content needs no resource pack. External models require the appropriate provider and its pack. Other Minecraft versions, Folia and other server software are not certified by this wiki.

## Install

1. Obtain the AxiomCulinary build from the maintainer. This documentation repository has no public JAR download.
2. Stop the server. Put **one** AxiomCulinary JAR in its `plugins` folder.
3. Install any optional dependencies you intend to use, then start the server.
4. Check that AxiomCulinary enabled successfully and run `/culinary` in game.
5. Open `plugins/AxiomCulinary/config.yml` for messages and visual feedback, and `plugins/AxiomCulinary/content/` for content definitions.

The supplied build is named `AxiomCulinary-0.13.0-SNAPSHOT.jar`; the filename itself does not configure the plugin. Do not install test/probe JARs alongside it.

## First configuration

Keep the defaults for your first test. Use the in-game recipe and crafting menus to see the recipes actually loaded on your server. An operator can provide test items with `/culinary give PlayerName tomato_seeds 8`.

After editing YAML, use `/culinary reload`. Restart the server to replace JARs or add/remove dependencies; do not use Bukkit's `/reload` for this.

Already running an older version? Follow [Updates and backups](Updates-and-Backups.md) before replacing the JAR.

[Documentation home](Home.md)
