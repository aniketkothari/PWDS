# Paediatric Wellness by Dr. Shilpa

A static marketing website for a paediatric clinic, built with [Astro](https://astro.build) and [Tailwind CSS](https://tailwindcss.com).

## Features

- **Navbar** — Fixed top navigation with logo, section links, and "Book Appointment" CTA
- **Hero** — Two-column layout with SVG illustration and floating stat cards (1000+ families, 15+ years)
- **Services** — Three-card grid: Well-Child Checkups, Vaccinations, Sick Visits
- **Testimonials** — Three parent testimonial cards with star ratings
- **Footer** — Contact details, quick links, and clinic tagline

## Tech Stack

- [Astro](https://astro.build) v5 — static site generator
- [Tailwind CSS](https://tailwindcss.com) v4 — utility-first styling
- Google Fonts — Nunito (headings) + Inter (body)
- Pure SVG illustrations — no external image assets required

## Getting Started

```bash
# Install dependencies
npm install

# Start dev server at http://localhost:4321
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Project Structure

```
src/
  components/
    Navbar.astro
    Hero.astro
    Services.astro
    Testimonials.astro
    Footer.astro
  layouts/
    BaseLayout.astro
  pages/
    index.astro
  styles/
    global.css
public/
  favicon.svg
```

## Design Tokens

| Token | Value | Usage |
|-------|-------|-------|
| Cream | `#F5F0EA` | Page background |
| Coral | `#E8856A` | Primary accent, buttons, highlights |
| Charcoal | `#2D2A26` | Primary text, footer background |
| Muted | `#7A7570` | Secondary / body text |
