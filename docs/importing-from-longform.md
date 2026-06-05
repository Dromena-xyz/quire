# Importing from Longform

Quire grew out of Longform and keeps the same bones, so existing Longform
projects come across cleanly. The importer never modifies or deletes anything
Longform owns: it only reads your Longform projects and creates new Quire ones.

## Run the import

Open **Settings, Quire**, find **Switching from Longform**, and choose **Import a
project**, or run the command **Import a Longform project**. Quire scans your
vault for Longform projects and shows what it found.

Before anything is written, a review screen spells out exactly what each
selection will do, so there are no surprises.

## Two modes

- **Copy** duplicates a project's scenes into a new folder and writes a fresh
  Quire index. Your original Longform project is left completely untouched, so you
  can run both side by side while you settle in.
- **In place** adds a Quire index next to the Longform one and records the
  Longform index as ignored, so Quire never touches it. The scene files are shared
  with Longform as they sit.

## Drafts and workflows

Longform projects can hold several drafts. Quire uses one index per project, so
each draft you pick imports as its own Quire project; the picker tells you this
before you commit. Same-named projects are kept distinct rather than merged.

Your Longform compile workflows come across too. Quire reads them from Longform's
plugin data and recreates the named workflow, so your export settings are not
lost. The two tools share the same built-in steps, so a workflow maps over
directly.

## After importing

Single-scene and very old (pre-2.0) Longform projects are not listed; keep using
those in Longform as they are. Everything else is yours to arrange in
[the scene list](the-scene-list.md), edit in a [Galley](galley.md), and export
with [Compile](compile.md).
