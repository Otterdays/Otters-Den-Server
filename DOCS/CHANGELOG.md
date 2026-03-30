<!-- PRESERVATION RULE: Never delete or replace content. Append or annotate only. -->
# CHANGELOG

## [Unreleased]
- Mod list: **embedded JSON** in `index.html` (`<script type="application/json" id="otterdays-mod-data">`); **removed `mods.json` and `fetch()`** so the site is purely static on GitHub Pages (no second file, no backend, works on `file://` too).
- Documentation: `DOCS/SUMMARY.md` (website quick map + `mods.json` contract), `DOCS/ARCHITECTURE.md` (static site + mod loader behavior), `DOCS/SCRATCHPAD.md` (last actions); append-only per preservation header.
- Landing page: **Mod list** section loads grouped entries from root `mods.json` (name, optional version/url/notes/category, plus optional top-level minecraft/loader/updated); nav + scroll-spy include `#mods`. `[AMENDED 2026-03-29]:` data source is now inline JSON in `index.html`, not `mods.json`.
- Landing page: light/dark theme (persisted), mobile nav drawer with backdrop, back-to-top, scroll-spy nav highlights, skip link, OG/Twitter meta for GitHub Pages, reduced-motion handling, hero gradient fallback when background image is missing, copy-IP clipboard fallback.

## [0.1.0] - 2026-03-26
- Initial project setup
- Added documentation structure

## [0.2.0] - 2026-03-26
- Enhanced README with banner visual and official website link
- Structured internal documentation mapping
