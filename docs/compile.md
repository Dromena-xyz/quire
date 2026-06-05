# Compile

Compile assembles your scenes into one finished manuscript: a clean, exported
file with the cuts and formatting you choose. It runs as an ordered list of small
steps, so you decide exactly how the raw scenes become the final document.

## Workflows and steps

A **workflow** is a named, ordered list of **steps**. Build one in the Compile
tab: add steps, drag to reorder them, and set each step's options. Quire ships a
default workflow you can use as is or copy and adjust.

Each step plays one of three roles, and steps run top to bottom:

- **Scene steps** transform every scene on its own, before the scenes are joined.
- **The join step** combines the scenes, in order, into a single manuscript.
- **Manuscript steps** transform the assembled manuscript as a whole.

The Compile tab flags a workflow whose steps are out of order (for example a
scene step placed after the join), so you can fix it before running.

## The built-in steps

- **Prepend title** adds a heading above each scene, numbered however you like.
- **Strip frontmatter** removes a scene's YAML frontmatter block.
- **Remove links** unwraps `[[wikilinks]]` and `[text](links)` to their visible
  text, leaving embeds alone.
- **Remove comments** strips `%% Markdown %%` and `<!-- HTML -->` comments.
- **Delete headers**, **Remove checkboxes**, **Remove callouts**, **Remove
  Dataview queries**, and **Remove strikethroughs** clear those elements when you
  do not want them in an export.
- **Concatenate text** is the join step: it merges the scenes with a separator
  you choose between them.
- **Add frontmatter** puts a YAML block at the top of the finished manuscript.
- **Save as note** writes the manuscript to a file in your vault.

Most steps have options, like which kinds of links or comments to remove, or the
separator placed between joined scenes. A blank-line separator is written as
`\n\n` in the field.

## Leave scenes out

Some scenes are notes-to-self you do not want in the export. Mark a scene as
**excluded** in the Compile tab and it is skipped for that workflow, without
leaving the project.

## Where the manuscript lands

The **Save as note** step's target sets the output path. You can template it:

- `$title` and `$project` fill in the project's title.
- Date tokens fill in the compile date.
- A leading `/` is vault-root-absolute; a leading `./` or `../` is relative to the
  project folder.

If a file already exists at the target, Quire confirms before overwriting it.

## Run it

Run **Compile current project** from the Compile tab or the command palette. Quire
reports where the manuscript was saved when it finishes.
