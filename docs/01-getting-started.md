# Getting Started

## Install

Quire is closed-source, so it installs from GitHub rather than Obsidian's
community plugin directory, which isn't accepting new closed-source plugins
for now. Install it one of two ways.

**With BRAT (recommended, stays up to date).**

1. Install [BRAT](https://github.com/TfTHacker/obsidian42-brat) from
   `Settings > Community plugins > Browse`.
2. In BRAT, choose **Add beta plugin** and enter `Dromena-xyz/quire`.
3. Enable **Quire** in `Settings > Community plugins`.

BRAT then keeps Quire current as new releases ship.

**By hand (you control updates).**

1. Download `main.js`, `manifest.json`, and `styles.css` from the
   [latest release](https://github.com/Dromena-xyz/quire/releases).
2. Put them in `<your vault>/.obsidian/plugins/quire/`.
3. Reload Obsidian, then enable **Quire** in `Settings > Community plugins`.

## Activate

Open `Settings > Quire`, paste your license key under **License**, and click
**Activate** (or press Enter in the key field). See [Licensing](10-licensing.md)
for how activation, devices, and offline use work.

## Make a Project

You can create a project two ways:

- **From the file explorer.** Right-click any folder and choose **New Quire
  project**.
- **From the command palette.** Run **Create new project**.

Either way, Quire asks for a name, makes a project folder for it, and opens the
Quire pane focused on it. A project can sit anywhere in your vault, but not
inside another project.

## Write, Arrange, and Assemble

That is the whole loop:

- **Write** in the scene notes like any other note.
- **Arrange** them in [the scene list](03-the-scene-list.md): drag to reorder,
  nest scenes under one another, and group as your draft takes shape.
- **Read or revise the whole thing** in a [Galley](04-galley.md), which stitches
  the scenes into one document and flows your edits back to each note.
- **Export** with [Compile](05-compile.md) when you want a single manuscript.

Coming from Longform? See [Coming from Longform](06-coming-from-longform.md).
