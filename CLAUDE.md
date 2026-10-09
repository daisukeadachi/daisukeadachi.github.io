# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal academic website of Daisuke Adachi, served by GitHub Pages from the `master` branch (user page `daisukeadachi.github.io`). GitHub Pages builds the Jekyll site on push; there is no CI, Gemfile, or test suite.

## Build / preview

- There is no `Gemfile`, so `jekyll serve` alone will fail to resolve the remote theme plugins. To preview locally, use the GitHub Pages gem set, e.g. `gem install github-pages` then `jekyll serve`, and open `http://localhost:4000`.
- Deploy = push to `master`.
- `_site/` and `.sass-cache/` are build output that happen to be tracked in git; GitHub Pages ignores them. Do not edit them by hand.

## Structure

- `_config.yml` -- uses `jekyll-theme-minimal`; sets site title and the sidebar logo image.
- `_layouts/default.html` -- overrides the theme's default layout (adds the Google Analytics gtag snippet, comments out the description/GitHub-profile links). All pages use `layout: default`.
- Pages are Markdown with YAML front matter: `index.md` (bio, links to CV/Research/Teaching), `research.md` (working papers, work in progress, publications), `teaching.md`, `others.md` (not currently linked from the index).
- `assets/` -- PDFs linked from pages: CV (`Daisuke_Adachi_CV_latest.pdf`, linked from `index.md`), papers in `assets/papers/`, teaching material in `assets/teaching/`, images in `assets/images/`.

## Editing conventions

- Old or retired content is kept as HTML comments (`<!-- ... -->`) in the Markdown pages rather than deleted; follow that pattern when removing items.
- To update the CV, replace `assets/Daisuke_Adachi_CV_latest.pdf` in place so the link stays stable. Paper drafts likewise use stable `*_latest.pdf` filenames.
- `research.md` entries follow the format: linked title, `(joint with ...)`, optional italic status (e.g. *Revision requested by ...*), and optional sub-bullets for press coverage.
