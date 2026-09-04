# Outline — a folding viewer for Obsidian notes

A single self-contained page (`index.html`, no build step, no dependencies)
that renders a note with the same collapsing/expanding behavior as
Obsidian's outline. It currently opens straight to **Mobile Barricade.md** —
baked right into the page, so there's nothing to upload each time.

Everything runs client-side in the browser — nothing is ever sent anywhere.

## Host it on GitHub Pages

1. Create a new repo (or use an existing one) and add `index.html` to it.
2. Push it to GitHub.
3. In the repo, go to **Settings → Pages**, set "Source" to your default
   branch, root folder.
4. GitHub gives you a URL like `https://yourname.github.io/reponame/`.

You can also just double-click `index.html` locally — no server needed.

## Swapping in a different note

Click **"Open another file"** in the top bar to load a different `.md` file
or paste text instead — useful for testing. To make the site always open to
a *different* note by default, replace the `EMBEDDED_NOTE` string near the
top of the `<script>` block with your new file's contents (Claude can
regenerate this for you any time you paste in a new note).

## What it supports

- Plain **tab/space-indented outlines** with no bullets at all — indentation
  alone creates nesting and fold arrows, exactly like this file and like
  Obsidian's own editor does for any indented line.
- Standard markdown too: `#`…`######` headings, `-`/`*`/`+` and numbered
  lists, Obsidian callouts (`> [!note]`, `> [!warning]-` starts collapsed,
  `> [!tip]+` starts expanded), fenced code blocks, bold/italic/
  strikethrough/highlight, inline code, links, and `[[wiki links]]` (shown
  as styled text).
- Light/dark theme toggle, "Expand all" / "Collapse all".

## What it doesn't do

It won't resolve `[[wiki links]]` to other notes, render embeds (`![[note]]`),
tables, or Dataview queries. If your notes lean heavily on those, say so and
it can be extended.
