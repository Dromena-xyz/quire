# Projects and scenes

Quire keeps everything in plain files you can read, edit, and back up without it.
There is no database and no hidden state in your prose.

## A project on disk

A project is a folder that contains:

- **An index file, `_quire_index.md`.** Its frontmatter records the project's
  scenes, their order, and their nesting. This is the one file Quire owns; you
  rarely need to open it.
- **Scene files.** Ordinary Markdown notes, one per scene. By default they live
  in the project folder alongside the index.

Because the order and structure live in the index, your scene files stay clean:
no ordering numbers in filenames, no metadata you did not write.

## Scenes

A scene is a note. In the Quire pane each scene is a row, shown in reading order
and numbered by its position (a nested scene reads as `1.2`, and so on). You can:

- **Add** a scene from the field at the foot of the list, or insert one above or
  below another from its menu.
- **Rename** a scene; Quire renames the file and keeps the order intact.
- **Delete** a scene; the file goes to your system trash and leaves the list.
- **Open** a scene by clicking its row.

Two scenes in one project cannot share a name, because the name is the filename.

## The index is the source of truth

If a scene file is missing (you moved or deleted it outside Quire), its row still
appears, marked as missing, until you restore the file or remove the entry. The
list reflects what the index says; the files fill it in.

Next: arrange your scenes in [the scene list](the-scene-list.md).
