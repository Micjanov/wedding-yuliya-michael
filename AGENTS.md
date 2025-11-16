# Agent Guidelines for Wedding Links Page

## Project Overview
High-performance static wedding links page. Single HTML file, no build system or dependencies. Optimized for accessibility, SEO, and performance.

## Commands
- **Local preview**: Open `index.html` directly in browser (no server required)
- **Deploy**: Push to GitHub → Settings → Pages → Select main branch
- **Validate**: Use W3C validator or `npx html-validate index.html` (if Node.js available)

## Code Style Guidelines
- **HTML Semantics**: Use `<header>`, `<nav>`, `<main>`, `<footer>`, `<time>` for proper structure
- **Accessibility**: Include `aria-hidden` for decorative elements; use semantic HTML over ARIA when possible; ensure focus states
- **CSS Architecture**: Organized sections with comments; design tokens in `:root`; mobile-first responsive
- **Naming Convention**: BEM-inspired kebab-case (`.link-btn`, `.link-content`, `.flower-ico`)
- **Color System**: All colors as CSS custom properties prefixed `--color-*` for easy theming
- **Typography**: Clamp() for fluid scaling; fallback fonts defined; reduced motion support
- **Performance**: Async font loading; `backdrop-filter`; optimized transitions with cubic-bezier
- **Indentation**: 4 spaces; organized CSS with section headers

## Customization Guide
- **URLs**: Search `REPLACE_ME` (4 occurrences) and update with Google Forms URLs
- **Content**: Update names in `<h1>` (line ~150), date in `<time datetime>` (line ~151)
- **Colors**: Modify `--color-*` variables in `:root` (lines ~40-50)
- **Fonts**: Remove Google Fonts links and update `--font-*` variables for system fonts only

## Key Improvements Over Original
- Semantic HTML5 (`<header>`, `<nav>`, `<time>`)
- Organized CSS with design tokens and section comments
- Better accessibility (focus states, reduced motion, print styles)
- Performance optimizations (async fonts, backdrop-filter, optimized shadows)
- SEO meta tags (OpenGraph, description, theme-color)
- Fluid typography with clamp() for better responsive scaling
