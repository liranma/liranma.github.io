# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal academic website for Dr. Liran Ma, built with Jekyll and the [academicpages](https://academicpages.github.io/) theme (based on Minimal Mistakes). It is hosted on GitHub Pages at [liranma.github.io](https://liranma.github.io).

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve --livereload

# Build for production
bundle exec jekyll build

# Push to GitHub (triggers automatic GitHub Pages build)
git push origin master

# Check build status
gh run list --limit 5

# View failed build logs
gh run view --log-failed
```

> **Note:** `gh` is installed via Homebrew. If not found, run `export PATH="/opt/homebrew/bin:$PATH"` first.

## Architecture

### Pages (`_pages/`)
The four active pages are:
- `about.md` — Home page (`/`), uses `classes: hide-title` to suppress the visible H1 while keeping the browser tab title
- `research.md` — Publications and AI projects
- `teaching.html` — Courses taught
- `news.md` — Recent news (new degree programs)

Navigation is defined in `_data/navigation.yml`.

### Styling (`_sass/`)
The theme uses a custom **navy/teal** color scheme with **Inter** font (loaded via Google Fonts in `_includes/head.html`).

Key SCSS files:
- `_variables.scss` — All colors, fonts, breakpoints. Primary color is `$navy: #1a365d`, link color is `$teal: #2b6cb0`.
- `_sidebar.scss` — Profile image is 200×200px circle (`border-radius: 50%`) with `object-position: center 30%` to center the face.
- `_masthead.scss` / `_navigation.scss` — Navy top bar with white nav links.
- `_page.scss` — Contains `.hide-title` class (used on home page) and `h2` section dividers.

### Sidebar (`_includes/author-profile.html`)
Displays: location, employer, URI, email, ResearchGate, LinkedIn, GitHub, Google Scholar, ORCID. Author name and bio are intentionally hidden (empty `author__content` div).

### CSS Specificity Warning
The Minimal Mistakes theme has strong default styles. **Inline styles on HTML elements are the most reliable way** to override image sizing (e.g., project images on the research page use inline `style=` attributes, not CSS classes).

### Deployment
Pushing to `master` triggers an automatic GitHub Pages build. Builds take ~1 minute. Always check `gh run list` after pushing to confirm success.

## Content Conventions

- **Publications**: Listed manually in `_pages/research.md` in standard academic format (authors, title, venue, year).
- **Project images**: Use inline styles with `float: left`, fixed `width`/`height`, `object-fit: cover`, and `overflow: hidden` on the wrapper `<div>`.
- **Hiding content**: Wrap in HTML comments `<!-- -->` rather than deleting, so it can be restored later.
- **Author info** (email, employer, social links): Update in `_config.yml` under the `author:` key.
