# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
pnpm dev        # Start dev server at localhost:4321
pnpm build      # Build for production (outputs to ./dist/)
pnpm preview    # Preview production build locally
```

Requires Node.js >=22.12.0 and pnpm.

## Architecture

This is an [Astro 6](https://astro.build) project — a static site generator with file-based routing and zero client-side JS by default.

- **Pages** (`src/pages/`) — each `.astro` file maps to a URL route; `index.astro` → `/`
- **Layouts** (`src/layouts/`) — base HTML wrappers using `<slot />` to inject page content
- **Components** (`src/components/`) — reusable `.astro` components
- **Public** (`public/`) — static assets served verbatim (no processing)
- **Assets** (`src/assets/`) — processed assets imported as modules

TypeScript is configured in strict mode via `astro/tsconfigs/strict`.

Component styles are scoped by default (written inside `<style>` tags within `.astro` files). No CSS framework is configured.
