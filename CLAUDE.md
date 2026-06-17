# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A static personal portfolio site — plain HTML and CSS, no build step, no framework, no package manager. Everything is served as-is.

## Serving locally

Open any `.html` file directly in a browser, or use any static file server:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## File structure

- `index.html` — main portfolio page (hero, research, publications, experience, projects, skills, education, contact)
- `pub-diffusion.html` — publication detail page for the ICCV 2025 diffusion paper
- `pub-trajectory.html` — publication detail page for the ACM ICEA 2024 trajectory paper
- `styles.css` — all styles shared across every page
- `profile.jpg` — hero photo

## Styling conventions

All CSS lives in `styles.css`. CSS custom properties (defined on `:root`) drive the entire colour palette and spacing — always use them rather than hardcoded values. Key tokens:

- `--accent` / `--accent-2` / `--accent-soft` — blue accent family
- `--paper` / `--surface` / `--surface-2` — background layers
- `--ink` / `--ink-2` / `--muted` / `--faint` — text hierarchy
- `--line` / `--line-strong` — border colours
- `--r` / `--r-lg` / `--maxw` / `--readw` — radius and width constraints

Three typefaces are loaded from Google Fonts: **Space Grotesk** (headings/brand), **Inter** (body), **JetBrains Mono** (metadata, tags, monospace labels).

The `.reveal` + `.in` pattern drives scroll-triggered fade-in animations via `IntersectionObserver` (in `index.html`'s inline `<script>`).

## Adding a new publication detail page

Copy the structure of `pub-diffusion.html` or `pub-trajectory.html`. Both use the `.article` layout class from `styles.css`. Then add a link to the new page in the `#publications` section of `index.html`.

## LinkedIn placeholder

`index.html` line 264 contains a placeholder LinkedIn URL (`https://www.linkedin.com/`). Replace it with the real profile URL when known.
