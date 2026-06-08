# Styling Your Scenes

Quire tags your writing surface with CSS classes so you can style it, and only
it, with an Obsidian CSS snippet. Your manuscript can wear a serif font and a
narrow page while the rest of your vault stays exactly as it is.

## The Classes Quire Adds

When you open a scene, a project's index, or a Galley, Quire adds a class to
that editor pane:

- **`quire-leaf`** is on every Quire writing surface: scenes, the project
  index, and Galleys. Target it to style all of your Quire writing at once.
- **`quire-galley`** is on a Galley only (the combined multi-scene editor).
  Target it to style the Galley distinctly.
- Inside a Galley, each scene break is a **`quire-scene-divider`** element
  carrying a **`data-quire-title`** attribute with that scene's title.

Quire ships these unstyled. They are hooks for your own CSS; Quire applies no
rules of its own to `quire-leaf` or `quire-galley`, so nothing changes until you
write a snippet.

## Adding a Snippet

1. Save a `.css` file in your vault's snippets folder,
   `<your vault>/.obsidian/snippets/`. Name it anything, such as
   `quire-writing.css`.
2. In Obsidian, open Settings, then Appearance, and under CSS snippets turn
   yours on. Use the refresh icon if it does not appear yet.
3. Edit the file and the page updates live.

## Coming From Longform

Longform offered a single hook, `.longform-leaf`. Quire's `.quire-leaf` is the
exact equivalent, so porting a snippet is one find and replace:

```
.longform-leaf   ->   .quire-leaf
```

Everything below works under `.quire-leaf`. The `.quire-galley` and scene
divider hooks are extra, with no Longform equivalent.

## Recipes

Copy any of these into your snippet and adjust to taste.

### A Light Page in a Dark Vault

Keep your dark theme everywhere, but write on a clean light page.

```css
.quire-leaf {
  --background-primary: #fdfdfb;
  --background-primary-alt: #fdfdfb;
  --background-secondary: #fdfdfb;
}
.quire-leaf .markdown-source-view {
  --text-normal: #1a1a1a;
  color: #1a1a1a;
}
.quire-leaf .view-header {
  background-color: #fdfdfb;
}
```

### A Manuscript Font

```css
.quire-leaf .markdown-source-view {
  --font-text: "iA Writer Duospace", "Courier Prime", "Courier New", monospace;
  --font-text-size: 18px;
}
```

Swap in any font you have installed: a serif like Baskerville for a book feel,
or Courier Prime for standard manuscript format.

### A Narrower or Wider Page

Obsidian calls this the readable line length. Turn it on first under Settings,
Editor, Readable line length. Then set the width:

```css
.quire-leaf {
  --file-line-width: 38rem;
}
```

Use `rem` or `ch` for a width that tracks your font size, or `px` for a fixed
measure.

### More Comfortable Line Spacing

```css
.quire-leaf .cm-contentContainer {
  line-height: 1.7;
}
.quire-leaf .markdown-source-view.mod-cm6 .cm-content > .cm-line {
  padding-bottom: 0.6em;
}
```

### First-Line Indents

The prose look, indenting the first line of each paragraph:

```css
.quire-leaf .markdown-source-view.mod-cm6 .cm-line {
  text-indent: 1.5em;
}
```

In the editor each paragraph is one `.cm-line`, so this indents the start of a
paragraph and leaves its wrapped lines flush, which is what you want.

### Standard Manuscript Format

Double spaced, monospace, and indented, the shape editors expect:

```css
.quire-leaf .markdown-source-view {
  --font-text: "Courier Prime", "Courier New", monospace;
  --font-text-size: 16px;
  line-height: 2;
}
.quire-leaf .markdown-source-view.mod-cm6 .cm-line {
  text-indent: 0.5in;
}
```

### Hide the Chrome While Writing

Strip the pane header and the inline title for a cleaner page. Because it is
scoped to `.quire-leaf`, the rest of your vault keeps its headers.

```css
.quire-leaf .view-header {
  display: none;
}
.quire-leaf .inline-title {
  display: none;
}
```

### A Simple Focus Dim

Fade every line but the one you are on. For true typewriter scrolling, where the
active line stays centered, use a dedicated plugin; that needs more than CSS.

```css
.quire-leaf .cm-line {
  opacity: 0.45;
  transition: opacity 0.15s ease;
}
.quire-leaf .cm-line.cm-active {
  opacity: 1;
}
```

## Styling Galleys

A Galley stitches your whole project into one editor, a natural place for a
manuscript look. Everything above works in a Galley through `.quire-leaf`. For
Galley-only adjustments, use `.quire-galley`.

The scene breaks inside a Galley are `quire-scene-divider` elements, each
carrying its scene title in `data-quire-title`. Quire styles them by default;
you can layer your own rules on top, for example to make them quieter:

```css
.quire-galley .quire-scene-divider {
  opacity: 0.5;
}
```

## A Few Notes

- These classes are a stable part of Quire. Snippets you write against them keep
  working across updates.
- The hooks sit on the editor pane, so your selectors usually reach inside with
  a descendant, like `.quire-leaf .markdown-source-view`.
- This is CSS only. It never touches your files. Turn a snippet off and your
  writing is exactly as it was.
