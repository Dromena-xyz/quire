# The scene list

The Quire pane shows your project as a list of scenes in reading order. This is
where you shape the draft.

## Reorder and nest

Drag a scene to move it. Quire offers two drop targets so reordering and nesting
are one gesture:

- **A line between rows** drops the scene there as a sibling, at that row's depth.
- **Highlighting a row** drops the scene in as that row's last child, one level
  deeper.

A parent carries its children: drag a scene with a subtree and the whole branch
moves together and keeps its shape. You can also move a scene with its menu:
**up**, **down**, **in** (indent), or **out** (outdent).

Scenes nest as deep as you like. A nested scene is numbered by its place in the
tree, so the second child of scene 1 reads as `1.2`.

## Collapse and expand

A scene with children shows a disclosure arrow. Collapse a branch to fold its
subtree away, or use the toolbar to collapse or expand the whole project at once.

## Select several at once

Hold the multi-select modifier (configurable in [Settings](settings.md)) and
click to select more than one scene. With a selection you can move, open as a
[Galley](galley.md), or act on all of them from the menu at once. Selecting a
parent brings its children along.

## Ignore and restore

Not every file in a project folder is a scene (notes, outlines, research). Mark a
file as **ignored** to keep it out of the scene list without deleting it. Ignored
files are listed in their own panel, where you can **restore** any of them back
into the project as a scene.

## The scene menu

Each row's menu collects its actions: rename, insert a scene above or below,
move, open in a Galley, ignore, and delete. The same actions apply to a
multi-selection where they make sense.
