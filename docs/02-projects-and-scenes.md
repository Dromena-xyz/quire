# Projects and Scenes

A Quire project is a normal folder of notes in your vault, arranged so you can
treat a long piece of writing as the many small parts it is really made of. There
is no database and no hidden state: your words live in plain Markdown notes you
can read, sync, and back up with or without Quire.

## What a Project Is

When you make a project, Quire creates a folder containing:

- **An index note, `_quire_index.md`.** Its frontmatter records the project's
  scenes and how they are ordered and nested. This is the one note Quire manages
  for you; you rarely open it.
- **Scene notes.** Ordinary Markdown notes, one per scene, kept in the project
  folder.

Because the order and structure live in the index, your scene notes stay clean.
Nothing is renamed with leading numbers, and no ordering metadata is written into
notes you are trying to write in.

## Scenes

A scene is just a note. In the Quire pane each scene is a row, shown in reading
order. Scenes can be nested into a parent and child outline, drawn with
indentation, so you can group a chapter's beats under the chapter, or a section's
scenes under the section, as deep as you like.

From a scene you can:

- **Open** it by clicking its row.
- **Add** a new scene from the field at the foot of the list, or insert one above
  or below another from its menu.
- **Rename** it. Quire renames the note and keeps its place in the order.
- **Delete** it. The note goes to your system trash and leaves the list.

Two scenes in one project cannot share a name, because the name is the note's
filename.

## The Index Is the Source of Truth

The list reflects what the index records; the notes fill it in. If a scene note
goes missing, because you moved or deleted it outside Quire, its row still appears
and is marked as missing until you restore the note or remove the entry. Your
structure is never lost just because a file moved.

Next, shape your draft in [The Scene List](03-the-scene-list.md).
