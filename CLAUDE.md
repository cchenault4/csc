# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
bundle install          # Install Ruby gem dependencies
bundle exec jekyll serve  # Start local dev server (http://localhost:4000)
bundle exec jekyll build  # Build static site to _site/
```

## Architecture

This is a **Jekyll static site** for author Dr. Christopher S. Chenault M.D., deployed to GitHub Pages at `christopherschenault.com`.

**Layouts** (`_layouts/`):
- `default.html` — base layout with `<head>`, nav include, and footer
- `book.html` — extends default; renders a book detail page from front matter fields (`title`, `subtitle`, `cover_image`, `buy_link`, `description`, `genre`, `pages`)

**Includes** (`_includes/`):
- `navigation.html` — site-wide nav, included by the default layout

**Pages** — root-level `.html` files (`index.html`, `covina-swept-away.html`, etc.) use Jekyll front matter to select a layout and pass data to it.

**Styles** — SCSS in `assets/css/`; the midnight remote theme provides base styles. Mobile breakpoint is 760px.

**Content flow**: page front matter → layout template → Liquid rendering → static HTML in `_site/`. Adding a new book means creating a new root `.html` file with the `book` layout and filling in the front matter fields.
