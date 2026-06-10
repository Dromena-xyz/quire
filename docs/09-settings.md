# Settings

Open Quire's settings from `Settings > Quire`. The options are grouped by area,
in this order.

## License

The first section, because nothing else in Quire works without it. Paste your key
and **Activate**, see your **Status** and **Activations**, use **Check status
now** to re-confirm on demand, and **Deactivate this vault on this device** to
free an activation for another machine. Full details are in
[Licensing](10-licensing.md).

## Updates

- **Version.** The installed version of Quire, with a note when a newer release is
  available.
- **Check for updates.** When on, Quire asks GitHub for the latest release when
  Obsidian starts and notes a newer version next to **Version**. Quire never
  installs updates itself.

## Scenes

- **Scene template.** A template applied to each new scene note. If you use the
  Templater plugin, its syntax is supported, so a new scene can start from your
  own boilerplate.
- **Write scene metadata.** When on, Quire writes two properties into each
  scene's frontmatter, `quire-order` and `quire-number`, for plugins like
  Dataview to query. Leave it off to keep scene notes free of any metadata you
  did not add; the index still tracks order either way.
- **Multi-select modifier.** Which click selects more than one scene at a time
  in the list: Alt/Option+click, or Cmd/Ctrl+Alt+click.

## Custom steps

Your library of [custom compile steps](12-custom-compile-steps.md): edit or
delete a step, or select **New custom step** to write one. Steps made here are
available to every project's compile workflows.

## Workspace

- **Hide pane on startup.** Keep the Quire pane closed when Obsidian launches, and
  open it yourself when you want it.

## Switching from Longform

- **Import a project.** Opens the importer. See
  [Coming from Longform](06-coming-from-longform.md) for how it works and what it
  does and does not touch.
