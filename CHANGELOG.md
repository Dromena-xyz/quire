# Changelog

Quire follows Semantic Versioning, `MAJOR.MINOR.PATCH`:

- **MAJOR** for a change that breaks how existing projects work or are stored.
- **MINOR** for a new, backward-compatible feature.
- **PATCH** for a backward-compatible fix.

Each release is published to GitHub (BRAT installs and updates from it) with its
notes mirrored here.

## [Unreleased]

### Added

- **Drafts.** Branch alternate versions of your project and rework them safely
  beside the manuscript. Create a draft from all scenes or just a selection,
  switch drafts from the Quire pane, merge scenes back (replace a scene's text
  in place, or add the draft's version as a copy, with nesting preserved), and
  promote a draft to become the manuscript outright. Galley and Compile follow
  the active draft, and a draft compiles into its own folder so exports never
  collide. See the new Drafts guide in the docs.
- **Multi-draft Longform import.** Copying a Longform project that holds
  several drafts now brings it in as one Quire project: the latest draft leads
  as the manuscript and the rest arrive as Quire drafts. Picking a single
  draft imports it as the whole project.

### Changed

- **Import review.** Each copy's destination folder is shown and editable
  before anything is written, with live name checking. A project that was
  already imported can be imported again under a new folder name. Clearer
  language and layout throughout the importer.
- **Compile pane.** The starter workflow can no longer be deleted (rename or
  duplicate it instead), workflows gained a Duplicate action, and the Save as
  note step stays pinned as the last step.
- **Confirmations.** Destructive dialogs (delete, promote, merge) are shorter,
  separating what happens from how to get things back.
- **Project settings.** Renaming a project commits with a Save button or
  Enter, instead of when the field loses focus.

### Fixed

- The importer reads Longform index files directly from disk, so a populated
  project no longer imports empty when Obsidian's metadata cache momentarily
  misreports it.
- An import whose folder was auto-numbered ("Novel 2") now takes its project
  name from that folder instead of keeping the original title.
- Deleting a parent scene no longer leaves its children behind as missing
  entries in the scene list.

## 1.1.0

### Added

- **Custom compile steps.** Write your own compile step in JavaScript, run in a
  sandbox with no file, network, or system access. Manage your steps in
  **Settings → Quire → Custom steps**, or create one inline from **Add step** in
  the Compile tab. A step runs per scene or on the whole manuscript depending on
  whether you place it before or after the join step, and a whole compile is
  capped by an overall time budget so a slow step cannot hang Obsidian. See
  [Custom Compile Steps](docs/12-custom-compile-steps.md).
- **Compile from the command palette.** A **Compile a project** command opens the
  Quire pane on the Compile tab so you can run a workflow without leaving the
  keyboard.
- **Scene styling hooks.** Quire now tags your writing surface with CSS classes
  so you can style it, and only it, with a snippet: `quire-leaf` on scenes, the
  project index, and Galleys, and `quire-galley` on Galleys. Coming from
  Longform, `.longform-leaf` maps to `.quire-leaf`. See
  [Styling Your Scenes](docs/11-styling-your-scenes.md).

### Changed

- **Save as note** now has separate **Folder** and **File name** fields instead
  of one path. The folder field autocompletes vault folders, both fields take the
  date and project placeholders, and a new step defaults to saving a note named
  after your project in the project folder.
- **The Compile tab is easier to read:** more space between steps, and a numbered
  badge on each.
- **Managing ignored scenes is smoother:** the "show ignored" toggle stays on as
  you switch tabs and projects, there is an **Unignore all**, and Cmd/Ctrl-click
  opens an ignored file in a new tab.
- **Collapse-all / expand-all** shows only the control that applies.

### Fixed

- Renaming an ignored scene no longer makes it reappear in a compile.
- Opening a Galley places the cursor in the first scene's text, not at the top of
  the temporary file.
- Closing a Galley no longer opens a duplicate tab for a scene you already had
  open.
- Dragging a scene no longer offers a drop that would not actually move it.

## 1.0.0

The first public release. Quire organizes a long writing project as ordered
scene files in Obsidian and brings them together when it is time to read or
export.

- **Scene list.** Every project is a tree of scenes you can drag to reorder and
  nest, select in bulk for one action, and ignore or restore without deleting.
- **Galley.** A combined editor that stitches a project's scenes into one
  document to read or revise as a whole, syncing each edit back to its scene.
- **Compile.** Named workflows of ordered, configurable steps assemble the
  scenes into a finished manuscript, with per-scene exclusion and templated
  output paths.
- **Import from Longform.** Bring existing Longform projects across without
  touching anything Longform owns, carrying their compile workflows with them.
- **Licensing.** Per-device activation that keeps working offline and stays out
  of your way.
