# Tasks: Minimalist Telegram Bot Landing + Blog

**Input**: Design documents from `/specs/1-minimalist-telegram-landing/`
**Prerequisites**: spec.md (required), research.md, data-model.md, contracts/, quickstart.md

**Tests**: Not requested; omit test tasks for now.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- Static site at repository root
- HTML at root and in `/blog/`
- CSS in `/css/`, JS in `/js/`

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure

- [ ] T001 Create folder structure: `/blog/`, `/js/` (if missing)
- [ ] T002 [P] Create `/blog/index.html` minimal scaffold using IDS tokens
- [ ] T003 [P] Create `/blog/post-template.html` minimal scaffold using IDS tokens
- [ ] T004 [P] Create `/js/main.js` and wire it in `layout-sample.html`

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core styles/behaviors required across user stories

**⚠️ CRITICAL**: No user story work can begin until this phase is complete

- [ ] T005 Define :focus-visible styles using tokens for ALL interactive controls across landing and blog:
   links, buttons, inputs, burger, mobile menu links in `css/ids.css` and `css/header.css`
- [ ] T006 [P] Ensure header/menu mobile overlay behavior is class-driven only in `layout-sample.html` and `css/header.css`
- [ ] T007 [P] Add anchor targets for in-page navigation (e.g., `#pricing`) in `layout-sample.html`
- [ ] T008 Ensure hover effects use only color/underline/background per tokens across `css/*.css`

**Checkpoint**: Foundation ready - user story implementation can now begin in parallel

---

## Phase 3: User Story 1 - Core Landing (Header, Hero, Primary CTA) (Priority: P1) 🎯 MVP

**Goal**: Пользователь мгновенно понимает ценность и видит явный путь действия

**Independent Test**: На десктопе и мобайле пользователь за ≤3 сек находит CTA и понимает 3 фичи из hero текста

### Implementation for User Story 1

- [ ] T009 [US1] Refine header nav: explicit underline links in `css/ids.css`/`css/header.css`
- [ ] T010 [P] [US1] Ensure CTA button hover uses `--ids__hover-RGB` in `css/header.css`
- [ ] T011 [P] [US1] Update hero copy per spec in `layout-sample.html` (H1, subcopy, 2 CTAs)
- [ ] T012 [US1] Add hero micro-demo placeholder block in `layout-sample.html` with accessible fallback

**Additional Implementation**

- [ ] T031 [US5] Add “How it works” 3 feature cards markup (пересылка/суммаризация/группировка) in `layout-sample.html` (section id `features`)

**Checkpoint**: US1 independently testable (open page, verify header/hero/CTA behavior)

---

## Phase 4: User Story 2 - Pricing Block (Anchor on Main) (Priority: P2)

**Goal**: Понятные мини-тарифы прямо на главной, доступные по якорю

**Independent Test**: Переход по `#pricing` приводит к блоку тарифов, различия очевидны

### Implementation for User Story 2

- [ ] T013 [US2] Create pricing section markup in `layout-sample.html` with id `pricing`
- [ ] T014 [P] [US2] Add minimal tier styles in `css/layout.css` or new `css/pricing.css`
- [ ] T015 [US2] Link header/menu item to `#pricing` in `layout-sample.html`

**Checkpoint**: US2 independently testable (anchor navigation, readability)

---

## Phase 5: User Story 3 - Blog (Index + Post Page) (Priority: P2)

**Goal**: Минималистичный блог в общем стиле IDS, читаемость и консистентность

**Independent Test**: `/blog/index.html` отображает список, кликабельные посты открывают `/blog/post-template.html`

### Implementation for User Story 3

- [ ] T016 [US3] Implement `/blog/index.html` list using IDS typography and underlined links
- [ ] T017 [P] [US3] Implement `/blog/post-template.html` with headings, figures, code styles
- [ ] T018 [US3] Add navigation back to main and consistent header/footer across blog pages
 - [ ] T032 [P] Update header and mobile menu links to point “Блог” → `/blog/index.html` in `layout-sample.html`

**Checkpoint**: US3 independently testable (navigate index → post; styles consistent)

---

## Phase 6: User Story 4 - Footer + Email Capture (Priority: P3)

**Goal**: Минималистичная форма e‑mail в футере без отвлечения от основного CTA

**Independent Test**: Форма видима, фокусируема, стили по токенам, без валидации на сервере

### Implementation for User Story 4

- [ ] T019 [US4] Add footer markup with email form to `layout-sample.html`
- [ ] T020 [P] [US4] Style footer and form using tokens in `css/layout.css` or `css/footer.css`
- [ ] T021 [US4] Add basic client-side validation (optional) in `/js/main.js`

**Checkpoint**: US4 independently testable (tab focus, submit disabled or no-op)

---

## Phase 7: User Story 5 - Media (Micro‑demos / Carousel) (Priority: P3)

**Goal**: Визуально показать фичи: микро‑демо или карусель скриншотов — по контексту

**Independent Test**: Демо(ы) грузятся быстро, уважают reduced-motion; карусель доступна с клавиатуры

### Implementation for User Story 5

- [ ] T022 [US5] Add micro‑demo component markup and styles in `layout-sample.html`/`css/layout.css`
- [ ] T023 [P] [US5] Implement lightweight play/pause logic in `/js/main.js` with reduced‑motion check
- [ ] T024 [P] [US5] Implement minimal screenshot carousel (prev/next, keyboard) in `/js/main.js`

**Checkpoint**: US5 independently testable (demo playback and/or carousel works; accessible)

---

## Phase N: Polish & Cross-Cutting Concerns

**Purpose**: Improvements that affect multiple user stories

- [ ] T025 [P] Ensure WCAG AA contrast for text and interactive states across `css/*.css`
- [ ] T026 [P] Add SEO metadata and OpenGraph tags in `layout-sample.html`
- [ ] T027 Optimize images/media (compress; use webp) in `images/`
- [ ] T028 Code cleanup: remove unused CSS, ensure tokens used everywhere
- [ ] T029 [P] Add consent banner (GA) markup + script loader (defer) in `layout-sample.html`/`/js/main.js`
- [ ] T030 Validate quickstart.md steps and update if needed
 - [ ] T033 Performance audit: run Lighthouse (desktop/mobile) and meet budgets LCP<2.0s, CLS<0.1, TBT<200ms
 - [ ] T034 Decide and enforce CSS nesting policy (no build step → de‑nest to valid CSS) across `css/*.css`
 - [ ] T035 Document analytics phase decision (MVP or post‑MVP); if MVP, move T029 to earlier phase

---

## Dependencies & Execution Order

### Phase Dependencies
- Setup (Phase 1): No dependencies
- Foundational (Phase 2): Depends on Setup; BLOCKS all user stories
- User Stories (Phase 3+): Depend on Phase 2; can proceed in priority order or parallel
- Polish (Final): After targeted user stories are complete

### User Story Dependencies
- User Story 1 (P1): After Phase 2; no other story deps
- User Story 2 (P2): After Phase 2; independent of US1 implementation details
- User Story 3 (P2): After Phase 2; independent of US1/US2
- User Story 4 (P3): After Phase 2; independent
- User Story 5 (P3): After Phase 2; independent

### Parallel Opportunities
- T002/T003/T004 can run in parallel during Setup
- T006/T007/T008 can run in parallel in Foundational
- Within stories, tasks marked [P] can run in parallel (separate files)

---

## Implementation Strategy

### MVP First (User Story 1 Only)
1. Complete Phase 1: Setup
2. Complete Phase 2: Foundational (CRITICAL)
3. Complete Phase 3: User Story 1
4. **STOP and VALIDATE**: Test US1 independently
5. Deploy/demo if ready

### Incremental Delivery
1. Setup + Foundational → Foundation ready
2. Add US1 → Test independently → Deploy/Demo (MVP)
3. Add US2 → Test independently → Deploy/Demo
4. Add US3 → Test independently → Deploy/Demo
5. Add US4/US5 → Test independently → Deploy/Demo
