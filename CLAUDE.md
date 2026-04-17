# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Goal

A single-page static site hosted and accessible on GitHub Pages (`hogdanish.github.io`) that renders `/src/content/modlist.md` as sortable tables. Dark mode, minimal/elegant design, mobile responsive.

## Commands

```bash
bun run dev      # Start dev server
bun run build    # Build for production
bun run preview  # Preview production build
```

## Stack

- **bun** — JavaScript runtime; used for development and build scripts
- **Astro 6** — static site generator; pages in `src/pages/`, layouts in `src/layouts/`
- **TailwindCSS 4** (via `@tailwindcss/vite` plugin) — configured in `src/global.css` with `@import "tailwindcss"`
- **DaisyUI 5** — loaded as a Tailwind plugin via `@plugin "daisyui"` in `src/global.css`
- **Tailwind Typography** — loaded via `@plugin '@tailwindcss/typography'` in `src/global.css`

## Architecture

The site is essentially a stub from `astro init` — the actual modlist feature still needs to be built. The key files to create/replace:

- `src/pages/index.astro` — currently shows default Astro welcome page; should be replaced to read and render `modlist.md`
- `src/layouts/Layout.astro` — base HTML shell with global CSS import; title is still "Astro Basics"
- `src/components/Welcome.astro` — default Astro welcome component; can be deleted once the modlist UI is built
- `src/content/modlist.md` — the data source; contains two markdown tables ("Current mod list" and "my Suggestions") with columns including Type, Name, Environment, and optionally Note

## Content Structure

`modlist.md` has two tables with slightly different schemas:
- **Current mod list**: `Type | Name | Environment`
- **my Suggestions**: `Type | Name | Note | Environment`

The Type column uses values: Library, Performance, QoL, Add-on, Content, Replacement. Name cells can contain `<br>`-separated lists of multiple mod names.
