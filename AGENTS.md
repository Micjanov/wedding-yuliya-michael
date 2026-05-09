# Agent Guidelines for Wedding Links Page

## Project Overview
Static wedding info page for Yuliya & Michael. Single HTML file, no build system or dependencies. Wildflower theme with palette derived from kleurenpalet.jpeg (lavender, marigold, cream, olive, forest green). Optimized for accessibility, SEO, and performance.

## Page Structure
Single scrollable page with these sections (in order):
1. **Language switcher** (EN / NL / RU)
2. **Hero** — names, date, location (Ghent/Gent/Гент), decorative sprig
3. **RSVP link** — links to Google Forms (per-language URLs)
4. **The Day (timeline)** — ceremony (Town Hall), walk & boat trip, festivity (Sint-Pietersabdij)
5. **Dress code** — no dress code, colour palette swatches
6. **Accommodation** — 5 hotel suggestions with price indicators
7. **Coming soon notice**
8. **Footer**
9. **Meadow decoration** (decorative SVG wildflower scene)

## Internationalisation (i18n)
- Three languages: English (default), Dutch, Russian
- All translatable text uses `data-i18n` attributes on HTML elements
- Translations live in a `translations` object in the inline `<script>`
- `setLang()` updates text content and swaps the RSVP link `href` per language
- Language preference saved to `localStorage`
- Hotel names are proper nouns and stay unchanged across languages; only address hints are translated

## Commands
- **Local preview**: Open `index.html` directly in browser (no server required)
- **Deploy**: Push to GitHub → Settings → Pages → Select main branch
- **Validate**: Use W3C validator or `npx html-validate index.html` (if Node.js available)

## Code Style Guidelines
- **HTML Semantics**: Use `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<time>` for proper structure
- **Accessibility**: Include `aria-hidden` for decorative elements; use semantic HTML over ARIA when possible; ensure focus states; `aria-label` on sections
- **CSS Architecture**: Organized sections with comment headers; design tokens in `:root`; mobile-first responsive
- **Naming Convention**: BEM-inspired kebab-case (`.link-btn`, `.timeline-item`, `.hotel-item`, `.flower-ico`)
- **Color System**: All colors as CSS custom properties prefixed `--color-*` for easy theming
- **Typography**: Clamp() for fluid scaling; fallback fonts defined; reduced motion support
- **Performance**: Async font loading; `backdrop-filter`; optimized transitions with cubic-bezier
- **Indentation**: 4 spaces; organized CSS with section headers
- **Section dividers**: Small decorative SVG wildflower sprigs between major sections

## Customization Guide
- **RSVP URLs**: Update `rsvp_url` in each language's translation object
- **Content**: Update names in `<h1>`, date in `<time datetime>`
- **Colors**: Modify `--color-*` variables in `:root`
- **Fonts**: Remove Google Fonts links and update `--font-*` variables for system fonts only
- **Hotels**: Edit the `.hotel-list` in the HTML and corresponding `hotel*_addr` translation keys
- **Timeline**: Edit `.timeline-item` articles and corresponding translation keys

## Key Features
- Semantic HTML5 with proper sectioning
- Organized CSS with design tokens and section comments
- Full i18n support (EN, NL, RU) with localStorage persistence
- Accessibility (focus states, reduced motion, print styles, aria labels)
- Performance optimizations (async fonts, backdrop-filter, optimized shadows)
- SEO meta tags (OpenGraph, description, theme-color)
- Fluid typography with clamp() for responsive scaling
- Colour palette swatches derived from kleurenpalet.jpeg

## Additional Files
- **create-translated-forms.gs** — Google Apps Script to create translated (NL, RU) RSVP Google Forms. Run via script.google.com.
- **contact-line-translations.txt** — Translated contact/question prompt lines (EN, NL, RU)

## Translation Guidelines
- Cross-check Russian translations via Google Translate API (`translate.googleapis.com`) to catch anglicisms and unnatural phrasing
- Avoid common pitfalls: "локация" (use "место"), repeated words (e.g. "прогулка и прогулка"), literal calques like "дайте нам знать" (prefer "не стесняйтесь обращаться к нам")
- Dutch translations should use natural informal register (jij/je, not u) matching a wedding invitation tone
