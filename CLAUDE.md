# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A [Frontend Mentor](https://www.frontendmentor.io) challenge: build a responsive testimonials grid section matching provided designs. No build tools — pure HTML/CSS, opened directly in a browser.

**Design targets:** mobile (375px) → tablet (768px / `48em`) → desktop (1440px / `90em`)

## Running the Project

Open `index.html` directly in a browser. There is no build step, dev server, package manager, or test suite.

## Architecture

**Single-page static site:**
- `index.html` — all markup
- `style/style.css` — all styles
- `images/` — profile photos + SVG background pattern
- `design/` — reference JPGs (mobile + desktop)

**CSS structure in `style.css`:**
1. `:root` — CSS custom properties for the full color palette and font sizes
2. Utility classes — composable `.text-color-*`, `.text-size-*`, `.text-weight-*`, `.bg-color-*` applied directly in HTML
3. Component styles — `.testimonials` (wrapper), `.testimony` (card base), `.testimony__header`, `.testimony__img`, `.testimony__user-info`
4. Grid layout — `.testimonials--grid-layout` with named grid areas (`daniel`, `jonathan`, `jeanette`, `patrick`, `kira`) defined at each breakpoint
5. BEM modifiers — `.testimony--<name>` assigns each card to its grid area; `.testimony--bg` adds the SVG quotation background on the Daniel card (tablet+)

**Grid layout progression:**
- Mobile: single-column implicit grid
- Tablet (`48em`): 2-column, 4-row explicit grid with named areas
- Desktop (`90em`): 4-column, 2-row explicit grid with named areas (Kira spans two rows on the right)

**Naming convention:** BEM — block (`testimony`), element (`testimony__header`), modifier (`testimony--daniel`, `testimony__header--flex-layout`).

## AI Assistant Role

See `AGENTS.md` for the full mentor persona. In short: the user is at a **Junior** level. Guide with hints and questions rather than writing solutions. Explain the *why*, encourage DevTools debugging, and let them write the code themselves.
