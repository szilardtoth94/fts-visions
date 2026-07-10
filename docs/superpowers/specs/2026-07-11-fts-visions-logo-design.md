# FTS Visions Logo Design

## Context

The site had a placeholder `logo.svg` (plain white Arial text, no background), which was actually broken: invisible on `Nav.astro`'s white background. `Footer.astro` reuses the same file on a dark (`bg-gray-900`) background. The favicon was still the default Astro starter icon, unrelated to the brand.

## Decision

A styled wordmark (no icon/symbol) — chosen after comparing an aperture/lens icon, a growth-arrow icon, a monogram badge, and a plain wordmark; wordmark won for being closest to the existing minimal identity while actually being legible.

## Design

**Primary logo** (`public/images/logo.svg`, 160×40, used at `h-8` in `Nav.astro`):
- Line 1: `FTS` bold (weight 800, ~20px), `.` in blue-600 (`#2563eb`)
- Line 2: `VISIONS` tracked out (letter-spacing 2.5, ~9px, weight 400), gray-500 (`#6b7280`)
- Text fill: near-black (`#111827`)
- For use on light backgrounds (Nav)

**Dark variant** (`public/images/logo-light.svg`, same layout/dimensions):
- Same structure, inverted for dark backgrounds: white `FTS`, blue-400 (`#60a5fa`) accent dot, gray-400 (`#9ca3af`) `VISIONS`
- For use on `Footer.astro`'s `bg-gray-900`

**Favicon** (`public/favicon.svg`, regenerate `public/favicon.ico`):
- Blue-600 (`#2563eb`) filled circle, white bold `FTS` centered
- Replaces the current default Astro starter icon

## Implementation

- Replace `public/images/logo.svg` content with the primary wordmark SVG
- Add `public/images/logo-light.svg` with the dark-variant SVG
- Update `Footer.astro`'s `<img src="/images/logo.svg" ...>` to `/images/logo-light.svg`
- Replace `public/favicon.svg` with the monogram SVG; regenerate `public/favicon.ico` from it
- No component structural changes needed — `Nav.astro`'s existing `<img>` tag and dimensions (128×32, `h-8`) are unchanged
