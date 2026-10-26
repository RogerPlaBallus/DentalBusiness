# Clínica Dental Tramuntana — Single Page Website

Fictional dental clinic in Barcelona, Catalonia. One-page marketing + booking site.

## Made with

- Claude Opus 4.5 (Anthropic)

## Stack used

- HTML5 (semantic sections)
- Tailwind CSS via browser CDN (no build step)
- Vanilla JS (IIFE, no framework)
- Google Fonts: Sora (display) + Inter (body)
- Inline SVG icons (hand-written, no icon package)
- Pexels photography (remote URLs)

## Architecture

- Single file: `index.html` — markup, CSS vars, and script inline.
- Design tokens in `:root` CSS custom properties (`--ink`, `--teal`, `--coral`, `--amber`, `--bone`, `--steel`, `--line`).
- Tailwind arbitrary values reference the same tokens (`bg-[var(--teal)]`).
- JS scope: one IIFE, 3 modules → nav toggle, scroll reveal (IntersectionObserver), form validation.
- No state store, no router, no build, no npm.

## Most important aspects

- Minimal, flat UI: no glow, no shadows-as-decoration, sharp radii + accent bars.
- Distinct color coding: teal = primary/clinical, coral = action/CTA, amber = accent/highlight, ink = structure.
- All copy in bullet points; zero filler paragraphs.
- Nav is sticky; mobile menu is a single hidden panel toggled by one button.
- Hero image + 4 team images + 1 clinic image, all `loading="lazy"` except hero.
- Booking form: native inputs only (`type="date"`, `type="email"`, `type="tel"`) + regex validation, `aria-live` status message.
- FAQ uses native `<details>`/`<summary>` — no JS accordion.
- Accessibility: skip-free landmarks, `sr-only` captions, visible focus ring, `prefers-reduced-motion` honored, alt text on every image.
- Zero backend: form validates and confirms locally, no data leaves the browser.

## Known ceilings

- `ponytail:` form submission is client-side only; wire to a real endpoint when bookings must persist.
- `ponytail:` prices/reviews are hardcoded demo data; move to a CMS only if content changes often.
- `ponytail:` no i18n switcher; the site is EN-only by design.

## How to install or download

No install. No dependencies to fetch.

1. Download / clone this folder.
2. Open `index.html` in any modern browser.
3. (Optional) Serve locally: `python3 -m http.server 8000` → `http://localhost:8000`

Deploy: upload `index.html` to Netlify, Vercel, GitHub Pages or any static host. Internet required only for the Tailwind CDN, Google Fonts and Pexels images.

## Made by

Roger Pla Ballús with Claude Opus 4.5 (Anthropic)
