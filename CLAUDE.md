# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # Start dev server at http://localhost:4321
npm run build     # Build for production (outputs to dist/)
npm run preview   # Preview the production build locally
```

No linting or test scripts are configured.

## Architecture

Static marketing site for a paediatric clinic, built with **Astro v5** and **Tailwind CSS v4** (via Vite plugin). No JavaScript frameworks, no backend, no CMS — all content is hardcoded.

### File Structure

```
src/
├── components/       # One .astro file per section
├── layouts/
│   └── BaseLayout.astro   # HTML shell, loads global.css and Google Fonts
├── pages/
│   └── index.astro        # Single page; imports all components
└── styles/
    └── global.css         # Tailwind import + CSS custom property theme tokens
public/               # Static assets (favicons)
```

### Component Hierarchy

`index.astro` wraps everything in `BaseLayout`, then renders:
`Navbar → Hero → Services → Testimonials → Footer`

### Design Tokens

All colors are CSS custom properties defined in `src/styles/global.css` under the `@theme` block:

| Token | Hex | Usage |
|---|---|---|
| Cream | `#F5F0EA` | Page background |
| Coral | `#E8856A` | Primary accent, buttons, icons |
| Charcoal | `#2D2A26` | Primary text, footer |
| Muted | `#7A7570` | Secondary text |
| Card | `#FFFFFF` | Card backgrounds |
| Card-bg | `#EEF7F4` | Alternate card/section backgrounds |

Use these tokens via Tailwind classes that map to these properties (e.g. `bg-cream`, `text-coral`) rather than hardcoding hex values.

Fonts are also defined as theme tokens: `--font-nunito` (headings) and `--font-inter` (body).

### Content

Data (services list, testimonials list) is defined inline inside the relevant component's frontmatter — there is no separate data layer or CMS.

## Deployment

The site is deployed via **Cloudflare Pages** with git integration.

`wrangler.toml` configures the Pages project (`pages_build_output_dir = "dist"`). Do **not** add a `[build]` section to `wrangler.toml` — it is unsupported for Pages projects and will cause deployment failures.

Cloudflare Pages handles deployment automatically after the build completes. No custom deploy command is needed in the Pages dashboard settings.
