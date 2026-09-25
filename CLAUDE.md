# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal academic website for Daniil Starikov (Ph.D. student, Harris School of Public Policy, University of Chicago). Plain HTML/CSS with no build step, no dependencies, no package manager, and no test suite — just four static pages sharing one stylesheet, plus downloadable PDFs.

## Structure

- `index.html` — home/bio page
- `research.html` — working papers and pre-Ph.D. research, each with a PDF draft
- `teaching.html` — TA positions and awards
- `olympiads.html` — economics olympiad involvement (competitor, jury, organizing)
- `style.css` — shared stylesheet for all four pages
- `cv.pdf`, `soviet-repression.pdf`, `formula1-sequential-games.pdf`, `nhl-superstar-economics.pdf` — draft/CV PDFs linked directly from the nav bar and from `research.html`; keep filenames lowercase and hyphenated (no spaces/parentheses) since they're referenced directly in `href`s
- `favicon.svg` / `apple-touch-icon.png` — "DS" initials mark (Georgia serif, oxblood on cream, matching the site palette); linked from the `<head>` of all four pages

There is no `cv.html` — the nav bar's "CV" link points straight at `cv.pdf` rather than an intermediate page, matching the pattern on comparable academic sites.

`soviet-repression.pdf` is listed in `.gitignore` on purpose: that paper is shared "on request" only (see its "Work in progress" entry in `research.html`, which has no `[PDF]` link), so the file must stay local and never get committed or pushed to GitHub Pages. Don't remove it from `.gitignore` or add a link to it without the user's explicit go-ahead.

Each HTML page repeats the same header/nav/footer markup independently (no templating). When editing shared chrome (nav links, footer text, the Google Analytics snippet), apply the change to all four files identically.

The footer's "Last updated" date is a hand-maintained string (no build step to generate it automatically) — bump it in all four files whenever a content change is pushed live.

## Conventions

- Highlight unfilled content with `<span class="placeholder">...</span>` (styled in `style.css`) rather than leaving TODOs in plain text — this is the pattern already used for things like `[Last Name]`, `[Advisor Name]`, and course names to be filled in.
- The Google Analytics snippet is commented out in the `<head>` of each page; if enabled, it must be pasted unchanged into all four files with the same Measurement ID.
- `research.html` renders publications with a hanging-indent, bibliography-style list (`.pub-list` / `.pub-title` / `.pub-meta` / `.pub-abstract` in `style.css`); `teaching.html` and `olympiads.html` use a simpler `.entry-list` pattern. Match the existing pattern for the page when adding entries.

## Workflow

No build, lint, or test commands — verify changes by opening the HTML files directly in a browser. Deployment is via GitHub Pages (repo named `<username>.github.io`, served from the `main` branch root with zero config); see `README.md` for full setup steps including the custom-domain and Google Analytics instructions.
