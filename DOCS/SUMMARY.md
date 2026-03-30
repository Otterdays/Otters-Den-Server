<!-- PRESERVATION RULE: Never delete or replace content. Append or annotate only. -->
# Project Summary
Project: Otter's Den Server
Description: Minecraft server website and documentation.
Status: README Enhanced & Website Linked

[AMENDED 2026-03-29]: The public landing page includes a **Mod list** section (`#mods`) that loads grouped data from **`mods.json`** at the repository root (same origin as `index.html` on GitHub Pages). Edit that JSON and redeploy to update the list; see `README.md` for a one-line pointer.

## Website (static) — quick map

| Artifact | Role |
|----------|------|
| `index.html` | Single-page layout, nav, sections, inline script (theme, nav, scroll-spy, mod list loader, copy-IP). |
| `styles.css` | Tokens, themes, layout, mod list row styles. |
| `mods.json` | Public mod catalog: optional top-level `minecraft`, `loader`, `updated`; required `mods` array of objects (`name` required; optional `version`, `url`, `category`, `notes`, `side`). |
| `assets/` | Images (hero, OG banner, etc.). |

**Local dev note:** Browsers block `fetch('mods.json')` from `file://`; serve the repo root with any static HTTP server to preview the mod list.

[AMENDED 2026-03-29]: **Mod list is no longer loaded via `fetch`.** The catalog is embedded in `index.html` as `<script type="application/json" id="otterdays-mod-data">` (parsed in-page). **`mods.json` removed** — GitHub Pages stays 100% static HTML/CSS/assets with **no backend** and **no extra HTTP round-trip** for mods. The table row for `mods.json` above is **obsolete**; treat the inline script block as the source of truth.
