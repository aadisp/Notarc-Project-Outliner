# Outline — a folding viewer for Obsidian notes

A single self-contained page (`index.html`, no build step, no dependencies) that
renders a Markdown file with the same collapsing/expanding behavior as
Obsidian's outline: foldable headings, foldable nested bullet/numbered lists,
and foldable callouts (`> [!note]-`).

Everything runs client-side in the browser — the file you open never leaves
your machine.

## Host it on GitHub Pages

1. Create a new repo (or use an existing one) and add `index.html` to it.
2. Push it to GitHub.
3. In the repo, go to **Settings → Pages**, set "Source" to your default
   branch, root folder.
4. GitHub gives you a URL like `https://yourname.github.io/reponame/`.
5. Open that URL, drop in (or "Choose a file…") your exported `.md` note.

You can also just double-click `index.html` locally — no server needed.

## What it supports

- `#` … `######` headings, foldable when they contain content
- `-`, `*`, `+` and numbered lists, nested by indentation, each foldable
- Obsidian callouts: `> [!note]`, `> [!warning]-` (starts collapsed),
  `> [!tip]+` (starts expanded)
- Fenced code blocks, bold/italic/strikethrough/highlight, inline code,
  links, and `[[wiki links]]` (shown as styled text)
- Light/dark theme toggle, "Expand all" / "Collapse all"

## What it doesn't do

It's a lightweight renderer, not a full Obsidian clone — it won't resolve
`[[wiki links]]` to other notes, render embeds (`![[note]]`), tables, or
Dataview queries. If your notes lean heavily on those, let me know and I can
extend it.
