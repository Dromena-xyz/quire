# Coming from Longform

Quire is its own tool, with its own model: one index per project, nested scenes,
the Galley, and a fresh codebase underneath. It is not a drop-in replacement for
Longform, and it does not try to be. What it does do is meet you where you are. If
your work lives in Longform today, Quire brings those projects across cleanly so
you can pick up in Quire without rebuilding anything by hand.

The importer is strictly non-destructive. It only reads your Longform projects
and creates new Quire ones; it never changes or deletes anything Longform owns.

## Migrate a Project

Open `Settings > Quire`, find **Switching from Longform**, and choose **Import a
project**, or run the **Import a Longform project** command. Quire scans your
vault and shows what it found. Before anything is written, a review screen spells
out exactly what each selection will do, so there are no surprises.

You choose how each project comes over:

- **Copy** duplicates a project's scenes into a new folder with a fresh Quire
  index. Your Longform project is left completely untouched, so you can run both
  side by side while you settle in.
- **In place** adds a Quire index beside the Longform one and marks the Longform
  index as ignored, so Quire never touches it. The scene files are shared with
  Longform where they sit.

## Drafts

A Longform project can hold several drafts, and Quire has
[drafts](13-drafts.md) of its own, so they come across together. Copy a
multi-draft project and it becomes one Quire project: the latest draft leads as
the manuscript, and the rest come in as Quire drafts inside it. The review
screen names which draft leads. If you would rather lead with a different one,
promote it after importing.

Importing in place keeps every file where it sits, so there each Longform draft
becomes its own Quire project, right where it lives.

## Compile Workflows

Your Longform compile workflows come across too. Quire reads them from Longform's
saved data and recreates each named workflow, since the two tools share the same
built-in steps. One difference: Longform's custom code steps run with full Node
access, while Quire's [custom steps](12-custom-compile-steps.md) are sandboxed for
safety, so a Longform script cannot carry over and run as is. A workflow that uses
one still imports; Quire brings the rest of its steps over and flags the script
step so you can recreate it as a custom step.

## What Is Not Imported

Quire imports multi-scene Longform projects. A single-document Longform project,
or one stored in a format Quire does not recognize, is left where it is for you to
keep using in Longform. Everything else is yours to arrange in
[the scene list](03-the-scene-list.md), write in a [Galley](04-galley.md), and
export with [Compile](05-compile.md).
