# How Quire Stores Your Work

Quire keeps everything in plain files inside your own vault. There is no database,
no cloud, and no proprietary format holding your writing. If you uninstalled Quire
tomorrow, your scenes would still be ordinary Markdown notes and your compiled
manuscripts would still be ordinary notes. You are never locked in.

This page lays out exactly where your work lives, both so you can trust it and so
you can troubleshoot if something ever looks off.

## A Project Is a Folder

Each project is a folder in your vault holding two kinds of file:

- **Scene notes.** Ordinary Markdown notes, one per scene, in the project's scene
  folder. They are notes like any other; the rest of Obsidian works on them
  normally.
- **One index note, `_quire_index.md`.** This is the only file Quire manages. Its
  frontmatter records the project's structure: which notes are scenes, their order,
  and how they nest. The scene notes themselves stay clean, with no ordering
  numbers in their names and no metadata you did not write.

## The Index Note

Everything Quire needs to rebuild your project sits under a single `quire` key in
the index note's frontmatter. A small project looks like this:

```yaml
---
quire:
  format: scenes
  workflow: Default Workflow
  sceneFolder: /
  scenes:
    - An Unexpected Party
    - - Took and Take
      - Pastries in the Pantry
    - Roast Mutton
  ignoredFiles: []
---
```

The `scenes` list is the heart of it: each entry is a scene's note name, in reading
order, and a nested list holds that scene's children. In the example, "Took and
Take" and "Pastries in the Pantry" are children of "An Unexpected Party."

| Field | What it holds |
| --- | --- |
| `format` | The project type. Quire projects are `scenes`. |
| `workflow` | The name of the compile workflow this project uses. |
| `sceneFolder` | Where the scene notes live, relative to the index. `/` is the project folder itself. |
| `scenes` | The ordered, nested list of scene note names. A nested list is a child group. |
| `ignoredFiles` | Files in the folder that Quire keeps out of the scene list. |
| `sceneTemplate` | A template applied to new scenes, when one is set. |
| `compileExclusions` | Scenes left out of a particular compile workflow, when any are. |
| `title`, `draftTitle` | The project's title label, when set. |

You normally never open this note, but nothing stops you. If you understand the
shape above, you can read it, back it up, or repair it by hand.

## Quire's Own Settings

Two things are not in your project folder:

- **Settings and compile workflows** live in Quire's plugin data, at
  `.obsidian/plugins/quire/data.json` in your vault. They travel with the vault.
- **Your license key** is kept in Obsidian's secure storage on the device where
  you activated it, not in the vault, so syncing your notes never carries the key
  around. See [Licensing](10-licensing.md).

## Why This Helps

Because it is all plain files:

- **You own your work.** Back it up, sync it, version it, or read it with any tool.
  Quire is a convenience over your files, not a container for them.
- **Moving and syncing are safe.** The index tracks scenes by name, so syncing a
  vault across devices, or rearranging files in Obsidian, does not lose your
  structure.
- **Problems are inspectable.** If a scene shows as missing in the list, its note
  was moved, renamed, or deleted outside Quire; find or restore the note, or remove
  its entry, and the list is whole again. The index note tells you exactly what
  Quire expects to find.
