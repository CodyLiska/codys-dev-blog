# CLAUDE.md — codys-dev-blog

> This file is read automatically by Claude Code at the start of every session.
> Keep this file updated as the project evolves.

---

## Memory Bank

At the start of every session, read these files from the Obsidian vault:

- `/Users/codyliska/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obfluence Home Lab/11_Claude-Memory/session-state.md` — working state snapshot from last session
- `/Users/codyliska/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obfluence Home Lab/11_Claude-Memory/lessons-summary.md` — known bugs index (check before debugging)
- `/Users/codyliska/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obfluence Home Lab/11_Claude-Memory/decisions-summary.md` — architectural decisions index (check before any arch decision)
- `/Users/codyliska/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obfluence Home Lab/11_Claude-Memory/conventions.md` — coding standards
- `/Users/codyliska/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obfluence Home Lab/11_Claude-Memory/recurring-tasks.md` — standing rules
- `/Users/codyliska/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obfluence Home Lab/11_Claude-Memory/projects/codys-dev-blog.md` — per-project deep context (if it exists)

Do NOT read session-log.md, decisions-log.md, or lessons-learned.md at startup — pull them on demand when relevant.

---

## Ending a Session

Before typing `/exit`, always tell Claude: **"wrap up this session"**

The global CLAUDE.md handles the full wrap-up checklist. Project file to update at wrap-up:
`/Users/codyliska/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obfluence Home Lab/11_Claude-Memory/projects/codys-dev-blog.md`

---

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Jekyll-based personal dev blog deployed to GitHub Pages. The site uses Tailwind CSS (via CDN) for styling with a dark theme and glass morphism design elements.

## Architecture

### Core Jekyll Structure
- `_config.yml`: Site configuration with Jekyll plugins (jekyll-feed) and kramdown markdown
- `_layouts/`: HTML templates for pages
  - `default.html`: Base template with Tailwind CSS, navigation, and footer
  - `post.html`: Blog post template extending default layout
- `_includes/sidebar.html`: Reusable sidebar component
- `_posts/`: Markdown blog posts following Jekyll naming convention `YYYY-MM-DD-title.md`
- `index.html`: Homepage with post listing, comment form, and sidebar

### Styling System
- Uses Tailwind CSS v3 via CDN with typography plugin
- Custom `.glass` CSS class for backdrop-filter blur effects
- Dark theme with neutral-900 background and slate-200 text
- Responsive grid layout (3-column on desktop, single-column on mobile)

### Content Structure
Blog posts use Jekyll front matter with:
- `layout: post`
- `title`, `date`, `categories`
- `excerpt_separator: <!--more-->`
- Optional `image` field for post thumbnails

## Development Workflow

### Local Development
This is a GitHub Pages compatible Jekyll site. To run locally:
```bash
bundle install
bundle exec jekyll serve
```

### Creating New Posts
1. Create files in `_posts/` with naming pattern: `YYYY-MM-DD-title.md`
2. Use the front matter template from README.md
3. Content before `<!--more-->` becomes the excerpt
4. Posts automatically appear on homepage in reverse chronological order

### Deployment
- Automatically deployed to GitHub Pages on push to main branch
- Site URL: https://codyliska.github.io/codys-dev-blog
- Uses baseurl: "/codys-dev-blog" for GitHub Pages subdirectory

## File Organization
- All styling is inline or via CDN (no local CSS files)
- No JavaScript framework - minimal vanilla JS for footer year
- No build process required beyond Jekyll's default processing
- Images should be placed in `/assets/images/` (referenced in README template)