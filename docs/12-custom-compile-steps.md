# Custom Compile Steps

When the [built-in steps](05-compile.md) do not cover a change you want to make,
you can write your own. A **custom step** runs a small piece of JavaScript on
your text during compile, so you can make bespoke cleanups, format conversions,
or any transform the built-in steps leave out.

Custom steps run in a **sandbox**: an isolated environment with no access to your
files, the network, or your system. A step can only read the text it is given
and return new text. It cannot reach anything else in your vault or on your
computer, so a stray step can change an export but never your work or your
machine.

## Write a Custom Step

You can write one in two places. While building a workflow, choose **Add step**
and pick **New custom step** to make one and drop it straight in. Or open Quire's
settings and, under **Custom steps**, choose **New custom step**. Either way,
give it a name, an optional description, and its code.

Your code is the body of a function that receives the text and returns the
transformed text:

```js
return text.replaceAll("...", "…");
```

- `text` is the content the step is given: one scene, or the whole manuscript
  (see below).
- Return a **string**, the transformed text. A step that returns anything else,
  throws an error, or runs too long is reported when you compile, named so you
  know which one, and the compile stops so nothing half-finished is written.

That is the whole contract: text in, text out. There is no `require`, no file
access, and no network.

Click **Test** to run your code on a sample scene and see its output, or any
error, before you use the step. The sample is a short stand-in, so a step that
relies on something it lacks may show an error there yet still work on your real
scenes.

## Where a Custom Step Runs

A custom step works like the built-in cleanup steps, and **its position in the
workflow decides what it sees.** Placed before the join step (the step that
combines your scenes into one manuscript), it runs on **each scene** in turn.
Placed after the join, it runs once on the **whole manuscript**. Add it to a
workflow with **Add step**, where it appears alongside the built-ins.

## Examples

**Straight quotes to curly quotes**

```js
return text
  .replace(/(^|[\s([{])"/g, "$1“")
  .replace(/"/g, "”")
  .replace(/(^|[\s([{])'/g, "$1‘")
  .replace(/'/g, "’");
```

**Collapse runs of blank lines into one**

```js
return text.replace(/\n{3,}/g, "\n\n");
```

**A plain find and replace**

```js
return text.replaceAll("teh", "the");
```

## Edit, Reuse, and Delete

Your custom steps live in one library, shared across every workflow, so a step
you write once can be added to as many workflows as you like. Manage the library
in Quire's settings, under **Custom steps**: edit or delete a step there, and the
change applies everywhere it is used. Delete a step and any workflow that used it
shows an **unloaded step** you can remove.

## Coming from Longform

Longform's user scripts run with full Node access: `require`, the file system,
and so on. Quire's custom steps are sandboxed instead, which is safer but means a
Longform script cannot be carried over and run as is. To bring one across,
recreate it as a custom step: paste the part that transforms the text, and drop
anything that reaches for files, the network, or Node modules. A script that was
only a text transform often moves over with little change.

When you import a Longform project whose workflow used a script, Quire tells you,
and the step shows as an unloaded step for you to replace.
```
