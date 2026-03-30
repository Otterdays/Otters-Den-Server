<!-- PRESERVATION RULE: Never delete or replace content. Append or annotate only. -->
# ARCHITECTURE
Basic HTML/CSS website.

## Public site (2026-03-29)

- **Stack:** Static files only (no bundler). `index.html` + `styles.css` + `assets/`.
- **Runtime behavior:** Inline IIFE in `index.html` handles theme (`localStorage`), mobile nav + backdrop, scroll-spy for section anchors, back-to-top, clipboard copy for server IP, IntersectionObserver for `.fade-in`, and **`loadModList()`** which `fetch`es **`mods.json`** from the document origin and builds grouped lists in `#mods-root` via `createElement` / `textContent` (no HTML injection from JSON fields).
- **Data contract:** `mods.json` is the source of truth for the public mod list. Optional document fields: `minecraft`, `loader`, `updated`. Each mod object requires `name`; optional `version`, `url` (http/https → link), `category` (default group `Other`), `notes`, `side`. Categories and names are sorted for display.
- **Deployment:** GitHub Pages must publish `mods.json` beside `index.html` (same path level). Local `file://` preview will not load the JSON unless a static server is used.

[AMENDED 2026-03-29]: **No `mods.json`; no `fetch` for the mod list.** The catalog JSON lives in **`index.html`** in `<script type="application/json" id="otterdays-mod-data">`. `loadModList()` reads `textContent` and `JSON.parse`s it, then builds `#mods-root` with `createElement` / `textContent`. **GitHub Pages:** still only static files—**no backend**, no API, no server-side rendering. Works the same on **`file://`** as on `https://…github.io/…`.
