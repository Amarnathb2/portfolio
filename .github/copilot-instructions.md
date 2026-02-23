# Copilot / AI Agent Instructions

Purpose: help an AI coding agent be immediately productive in this small static portfolio repo.

Big picture
- This is a static, single-page cinematic portfolio (no build system). Primary entry points: [index.html](index.html) and [test.html](test.html).
- Styling lives inline in each HTML head; interactivity is plain browser JS (typing effects, auto-scroll, reveal animations).

What to change and why
- Small UI tweaks: update inline CSS in the `<style>` block near the top of the file you edit (`index.html` or `test.html`).
- Add sections by inserting a new `<section>` with a `.content` child. Follow the existing pattern: `.from-left` / `.from-right` classes and toggle `.show` to reveal.
- JS effects live at the bottom of each HTML file inside `<script>` tags—edit there for timing, text, and scroll behavior.

Developer workflows (how to run & debug)
- Local preview: run a simple static server from the repo root and open `http://localhost:8000/index.html`.
  - Python: `python -m http.server 8000`
  - Windows (if multiple Pythons): `py -3 -m http.server 8000`
- Alternative: use VS Code Live Server extension to preview and get live reload.
- Debugging: use browser DevTools console—most runtime errors will be missing IDs or querySelector failures (e.g. `document.getElementById('typing')`). Check element IDs at top of each file.

Project-specific conventions & patterns
- Section pattern: each page uses full-viewport `<section>` blocks and a centered `.content` element. Reuse `.content` + `.from-left`/`.from-right` + `.show` for consistent animations.
- Typing & reveal helpers: small custom functions at the bottom of the HTML files (search for `typeEffect`, `typeText`, `autoScroll`, `revealNext`). Modify these rather than adding heavy libraries.
- Fonts & external assets: Google Fonts are loaded via link tags; avoid replacing with build tooling—keep it simple.

Integrations & external dependencies
- No backend or package manager. External dependencies: Google Fonts and browser APIs only. No CI, tests, or node tooling detected.

If you need to add tests or tooling
- Propose a plan before adding new toolchains (e.g., `npm`, `parcel`). This repo is intentionally minimal—prefer simple HTML/CSS/JS changes unless user requests a full refactor.

Examples (common edits)
- To add a new project section, copy an existing `<section id="projects">...</section>` block, update its content, and ensure `.content` has the same classes used elsewhere.
- To change typing text in `index.html`, edit the `text` constant near the bottom of the file (search for `const text=`).

Notes for the human reviewer
- I didn't find existing AI-agent docs in this repo; I created this file to capture discoverable, actionable patterns.
- Tell me if you want stricter commit/PR guidelines, or if you want me to introduce a lightweight dev server config or build pipeline.

Next steps
- Want me to open a PR, run a preview, or expand this doc with explicit code snippets? Reply with which you prefer.
