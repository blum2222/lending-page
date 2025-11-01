# Minimalist Telegram Bot Landing + Blog

## Overview
- Goal: Modern minimalist landing for a Telegram bot with a strong "for insiders" aesthetic, extremely clear value communication, and a seamless blog.
- Tone: Minimal, confident, approachable. No heavy corporate tone. Consistent studio‑level visual language.
- Tech: HTML, CSS, JS. Tokenized, responsive, accessible.

## Clarifications
### Session 2025-11-01
- Q: Pricing presentation? → A: Block on main page with anchor (A)
- Q: Blog content source? → A: Static HTML pages (A)
- Q: Email capture form & placement? → A: In footer, minimalist (B)
- Q: Feature media style? → A: Micro‑demos and/or screenshot carousel depending on context (B, D)
- Q: Analytics & consent? → A: Google Analytics + consent banner (B)

## Actors
- Visitor: First-time user discovering the bot.
- Returning user: Comes back to install, read blog, or share.
- Content editor: Publishes blog posts and edits landing copy.
- SEO crawler: Indexes landing and blog content.

## Core Value Propositions
- Пересылка сообщений: Transfer/forward messages efficiently.
- ИИ суммаризация: AI summarization to save time.
- Группировка каналов по интересам: Organize channels by interest.

## Information Architecture
- Header: Brand, explicit nav with underlined links, primary CTA.
- Hero: One-liner value proposition, short sub-copy, primary and secondary CTAs.
- How it works: 3 focused cards (Forwarding, AI summary, Grouping) with micro‑demos or short clips.
- Use cases: Real scenarios, short bullets, benefits.
- Pricing: Minimal block on main page (anchor link) with key differentiators.
- Social proof: Optional minimal testimonials/logos.
- Blog: Minimal list layout, excellent typographic rhythm, consistent tokens.
- Footer: Links (privacy/terms/contact), minimalist social, email capture form.

## Design System Requirements
- Tokens: All colors via CSS variables (RGB tokens). No hardcoded literals. Density `--ids__density` drives spacing and line-height. Radius `--ids__radius` for rounded utilities.
- Interactive clarity: Header nav links underlined. CTA hover uses positive/hover token; no blur/shadow.
- Minimalism: Avoid heavy shadows/glows/filters. Flat, token-driven color shifts.
- Consistency: BEM naming (`block__element--modifier`), utilities `ids__*`. Spacing via `ids__space` and containers via `ids__wrapper`.
- Blog consistency: Same typography, spacing, links, and tokens.

## Accessibility
- Focus-visible states for all interactive elements.
- Sufficient contrast for text and states.
- Semantic HTML (landmarks, headings order). Correct roles for links/buttons.
- Respect reduced motion for media (no auto-play if user prefers reduced motion).

## Performance
- Critical CSS for above-the-fold.
- Lightweight assets, compressed images/media (<300KB per micro‑demo where feasible).
- No blocking scripts; defer analytics.
- Targets: LCP < 2.0s (3G-like), CLS < 0.1, TBT < 200ms.

## Analytics & SEO
- Google Analytics with consent banner per clarification. Script deferred.
- Metadata: title, description, social preview.
- Blog indexable; semantic headings; optional structured data.

## Functional Requirements
- FR1: Header with underlined nav links; hover color uses `--ids__hover-RGB`.
- FR2: Primary CTA hover changes background to positive token; readable text.
- FR3: Burger menu overlays mobile menu; body scroll lock while open.
- FR4: Hero shows H1, subcopy, two CTAs.
- FR5: Three feature cards with keyboard access; media per context (micro‑demo or carousel).
- FR6: Blog index (list/grid) and post pages as static HTML; styles consistent with landing tokens.
- FR7: All interactive controls have `:focus-visible` styling.
- FR8: Responsive ≤767px: hide menu, show burger; wrappers adjust per utilities.
- FR9: Hover effects limited to color/underline/background; no glows/filters.
- FR10: Pricing block on main page with anchor link.
- FR11: Footer includes minimalist email capture form.
- FR12: Analytics implemented with consent banner.

## Non-Functional Requirements
- NFR1: Initial page weight < 200KB (excluding hero image).
- NFR2: LCP < 2.0s, CLS < 0.1, TBT < 200ms.
- NFR3: WCAG AA contrast for text and interactive elements.

## Success Criteria
- SC1: User understands product within 5 seconds of hero.
- SC2: ≥80% of test users find and click "Начать пользоваться" within 3 seconds.
- SC3: Bounce rate on hero reduced vs baseline by 20% (if baseline exists).
- SC4: Blog pages match landing tokens/styles without drift.

## Key Entities
- Post: title, slug, date, excerpt, content (HTML), cover (optional).
- FeatureCard: title, description, icon/media.
- MenuItem: label, href, order.

## User Scenarios & Acceptance Tests
- Scenario A: First-time visitor understands product
  - Given: Landing loads
  - When: User scans hero
  - Then: They can explain 3 core features
  - Test: 5 users; ≥4/5 pass

- Scenario B: CTA clarity
  - Given: Landing loads
  - When: User looks at header/hero
  - Then: Finds and clicks primary CTA ≤3s

- Scenario C: Blog consistency
  - Given: User opens a blog post
  - Then: Link styles, typography, spacing match landing standards

- Scenario D: Mobile nav
  - Given: ≤767px
  - When: Tap burger
  - Then: Overlay opens, body locked, links underlined

## Risks
- Scope creep into CMS before launch; mitigate with static HTML blog v1.
- Overuse of media; enforce <300KB per micro‑demo and respect reduced motion.

## Assumptions
- Single-language (RU) initially.
- Static hosting (no server code required).
