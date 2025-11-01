# Quickstart

## Structure
- /layout-sample.html — base landing markup
- /css/* — IDS tokens and components (reuse)
- /blog/index.html — blog list (to add)
- /blog/post-*.html — blog posts (to add)

## Build/Run
Static site. Open `layout-sample.html` in browser or serve folder via any static server.

## Implement next
1. Header
   - Underlined nav, CTA hover uses tokens
   - Burger + overlay mobile menu
2. Hero
   - H1 + subcopy + two CTAs
   - Optional micro‑demo placeholder
3. Pricing (anchor on main)
   - Minimal tiers, clear diff
4. Blog (HTML)
   - blog/index.html list
   - blog/post-template.html
5. Footer
   - Email capture form (static)
6. Consent banner + GA (defer)

## Tokens to use
- Colors: `--ids__text-RGB`, `--ids__link-RGB`, `--ids__hover-RGB`, `--ids__accent-RGB`, `--ids__surface-RGB`, `--ids__background-RGB`
- Layout: `ids__wrapper`, `ids__space`, `ids__rounded`, `ids__sequence`
- Typography: `.ids h1..h6`, `.XS/.S` modifiers

## Accessibility
- :focus-visible for links/buttons
- Respect reduced motion
- Semantic headings order
