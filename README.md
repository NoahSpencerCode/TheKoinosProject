# The Koinos Project

An ordinary English rendering of the Greek New Testament.

*Koinos* (κοινός) means common, shared, ordinary — the same word scholars use for the everyday Greek these documents were written in. The originals were ordinary literature in their own time. This project translates them the way translators handle non-religious Greek texts of the same era: modern everyday vocabulary, natural grammar, continuous prose with no chapter or verse numbers, and none of the sacral-pseudo vocabulary (sin, church, baptize, gospel, repent…) that later tradition layered over plain Greek words like *error*, *assembly*, *immerse*, *good news*, and *change your thinking*.

## Contents

- `koinos_data.json` — the book data: introduction essay, translation principles, per-page Greek/English pairs, and the clickable-word lexicon (Greek form, ordinary variants, secular usage example).
- `METHODOLOGY.md` — working methodology, the fixed rendering glossary, source pipeline, and current status.

## Status

Matthew complete: 71 pages of continuous Greek/English prose, 235 lexicon entries. Reader is built. Next book: Mark (or a consistency pass on Matthew).

## Read it

- `index.html` — the reader. Open it directly (double-click) or serve the folder; it loads `koinos_data.js` / `koinos_data.json`.
- `koinos_reader.html` — fully self-contained single file (data inlined), handy for sharing.

The reader is mobile-first: swipe to turn pages, tap any underlined word for its Greek and ordinary meaning, and use the bottom bar — search on the left, index on the right.

## Publish with GitHub Pages

1. Create a new GitHub repository (e.g. `TheKoinosProject`) and push this folder:
   ```
   git remote add origin https://github.com/YOURNAME/TheKoinosProject.git
   git push -u origin main
   ```
2. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, then pick **main** and **/ (root)** and save.
3. After a minute the book is live at `https://YOURNAME.github.io/TheKoinosProject/`.

Everything uses relative paths and the `.nojekyll` file is included, so no build step or configuration is needed.

## Greek source

SBL Greek New Testament (Greek text only; no English translation consulted), critical sigla removed, formatted as continuous prose to reflect the earliest manuscripts, which carry no chapter or verse numbers.
