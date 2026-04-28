# Y Soft Deck Library

Single GitHub Pages site that hosts a gallery of standalone HTML decks.

**Live:** https://hyderkhan.github.io/presentations/

## Layout

```
presentations/
├── index.html             ← gallery landing page
├── README.md
├── hca-healthcare/        ← HCA Healthcare Value Alignment Meeting
│   ├── index.html
│   ├── styles.css
│   ├── deck-stage.js
│   ├── assets/
│   └── fonts/
└── techu2026/             ← SAFEQ Cloud · TechU Virtual 2026
    ├── index.html
    ├── styles.css
    ├── deck-stage.js
    ├── assets/
    └── fonts/
```

Each deck is a self-contained static folder. `index.html` at root is the
gallery; clicking a card opens that deck at `./<deck-slug>/`.

## Adding a new deck

1. **Build the deck** in its own folder with `index.html`, `styles.css`,
   `deck-stage.js`, `assets/`, and `fonts/`. The existing two decks make
   good starting templates.

2. **Drop it into this repo** as a new top-level folder using a kebab-case
   slug, e.g. `acme-keynote/`:

   ```sh
   rsync -a --exclude='.git' --exclude='.gitignore' --exclude='README.md' \
       /path/to/source-deck/  acme-keynote/
   ```

3. **Add a card to the gallery** in `index.html`. Find the block of
   `<a class="card" href="./..."> ... </a>` entries and copy one as a
   template. Update:
   - `href` → `./acme-keynote/`
   - card title, subtitle, date, slide count
   - card accent (orange / teal / ink)

4. **Commit & push:**

   ```sh
   git add . && git commit -m "Add acme-keynote deck" && git push
   ```

   GitHub Pages rebuilds in about 30 seconds.

## Syncing an updated deck

If a deck is also maintained in a separate repo (e.g.
[Hyderkhan/HCA-Healthcare](https://github.com/Hyderkhan/HCA-Healthcare)
or [Hyderkhan/TechU2026](https://github.com/Hyderkhan/TechU2026)), refresh
the copy here with:

```sh
rsync -a --delete --exclude='.git' --exclude='.gitignore' --exclude='README.md' \
    /path/to/HCA-Healthcare/  hca-healthcare/

git add hca-healthcare/ && git commit -m "Sync hca-healthcare to latest" && git push
```

`--delete` removes files that no longer exist in the source so the copy
stays clean.

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000/
```

## Notes

- Each deck has its own `<deck-stage>` runtime; they don't share state.
- All asset paths are relative (`assets/...`), so each deck folder is
  fully self-contained and movable.
- The gallery uses no build tool — pure HTML + inline CSS — so editing
  it is just editing `index.html`.
