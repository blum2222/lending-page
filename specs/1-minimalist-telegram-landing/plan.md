# Implementation Plan: Minimalist Telegram Bot Landing + Blog

## Tech Stack
- Static site: HTML, CSS, JS (no build step)
- Design System: IDS tokens (colors, density, radius), utilities, BEM
- Hosting: static (any static server)

## Structure
- Root landing: `layout-sample.html`
- Blog: `/blog/index.html`, `/blog/post-*.html`
- Assets: `/css/`, `/images/`, `/js/`

## Design Tokens & Conventions
- Colors via `:root` RGB tokens; no hardcoded colors in components
- Spacing via `--ids__density`; radius via `--ids__radius`
- Typography per `.ids h1..h6` with `.XS/.S` modifiers
- BEM naming for components; utilities prefixed `ids__`

## Responsiveness
- Primary breakpoint: 767px (menu/burger, wrappers)

## Accessibility
- :focus-visible for links, buttons, inputs; visible outlines using tokens
- Semantic HTML, correct roles, reduced motion respected

## Performance Budgets
- LCP < 2.0s (3G-like), CLS < 0.1, TBT < 200ms
- Media budget: <300KB per micro‑demo where feasible
- Defer non-critical scripts (analytics)

## Analytics & Consent
- Google Analytics with consent banner, script `defer`, non-blocking

## Phasing
- MVP: US1 (Header/Hero/CTA)
- Then: US2 (Pricing), US3 (Blog), US4 (Footer email), US5 (Media)

## CSS Nesting Policy
- No build step → use valid CSS only (de‑nest where needed)
