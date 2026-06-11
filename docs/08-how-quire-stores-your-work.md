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

A project with [drafts](13-drafts.md) also holds one subfolder per draft, each a
small project of its own: the same two kinds of file, one level down.

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
    - The Green Light
    - - Hold Your Tongue
      - A Great Uncle
    - Ash and Gasoline
  ignoredFiles: []
---
```

The `scenes` list is the heart of it: each entry is a scene's note name, in reading
order, and a nested list holds that scene's children. In the example, "Hold
Your Tongue" and "A Great Uncle" are children of "The Green Light."

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
| `activeDraft` | Which [draft](13-drafts.md) the pane is acting on, when the project has drafts. |

You normally never open this note, but nothing stops you. If you understand the
shape above, you can read it, back it up, or repair it by hand.

## Files and Folders Quire Leaves Alone

Quire manages only your scene notes and the index. Everything else in a project
folder is yours to organize as you like:

- **A stray note** in the scene folder, one that is not in the scene list,
  shows in the Quire pane as *untracked*. Quire never pulls it in or changes it
  on its own; you choose whether to add it as a scene or have Quire ignore it.
- **A subfolder is left alone, with one exception.** Quire reads only the
  notes that sit directly in the scene folder, so you can keep research, images,
  outlines, or loose notes in a subfolder without any of it ever showing up as a
  scene. Nothing is hidden or moved; it simply isn't Quire's concern. The
  exception is a subfolder holding its own `_quire_index.md`: inside a project,
  that is one of the project's [drafts](13-drafts.md), and anywhere else it is
  simply another Quire project.

The rule is simple: a folder needs a `_quire_index.md` to mean anything to
Quire. Without one, it stays out of the way.

One folder is Quire's own: [Galley](04-galley.md) working files live in a
vault-root folder named `Quire`, which Quire hides from Obsidian's file
explorer to keep it out of your way. It still shows up in search and the quick
switcher. If you keep a root folder of your own named `Quire`, it is hidden
along with it; rename yours to see it in the explorer again.

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
