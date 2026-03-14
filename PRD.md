# FORMA Agency — Product Requirements Document

**Version:** 1.0
**Date:** March 2026
**Status:** Active

---

## 1. Overview

FORMA is a premium personal branding agency website for Southeast Asia's most exclusive personal branding consultancy. The site serves as both a marketing asset and an intake funnel — positioning FORMA as invitation-only and building qualified demand from founders, executives, and cultural leaders.

**Live URL:** TBD
**Primary market:** Southeast Asia (Philippines, Singapore) with global reach across 38 markets

---

## 2. Goals

| Goal | Metric |
|------|--------|
| Communicate exclusivity and authority | Bounce rate < 40%, avg. time on page > 2.5 min |
| Capture qualified intake requests | Form conversion rate ≥ 8% of unique visitors |
| Establish brand credibility | Social proof visible within first scroll |
| Drive waitlist signups | Q2 2025 cohort filled to capacity (4 spots) |

---

## 3. Target Users

### Primary: High-achieving professionals seeking brand authority
- Founders of funded startups
- C-suite executives in finance, tech, real estate
- Creative directors and cultural leaders
- Ages 28–50, Southeast Asia + diaspora

### Secondary: Referrers and media
- Journalists and PR professionals researching FORMA clients
- Investors and board members who encounter FORMA-branded clients

---

## 4. Pages & Sections

### 4.1 Navigation
- **Logo:** FORMA wordmark (mono, spaced, uppercase)
- **Links:** Studio · Work · Team · Contact
- **CTA pill:** "Get Invited" → anchors to intake form
- **Behavior:** Transparent on load, frosted glass + shadow on scroll (`stuck` class)
- **Mobile:** Hamburger menu (links and pill hidden at ≤ 768px)

### 4.2 Hero
- **Headline:** "Build / Your / Icon." — 3-line Playfair Display, 900 weight
- **Subheadline:** Agency positioning statement
- **CTAs:** "Request an Invite" (primary) + "See Our Work" (secondary text link)
- **KPIs:** 120+ Icons Built · 38 Global Markets · 97% Retention
- **Right panel:** Editorial portrait placeholder with floating recognition card (Forbes 30U30)
- **Animations:** Staggered fade-up on load (0.2s → 1.1s delays)

### 4.3 Marquee Strip
- Continuous scrolling ticker on rust background
- Services listed: Personal Branding, Visual Identity, Executive Positioning, Narrative Strategy, Media Architecture, Digital Presence, Legacy Building, Network Design
- Highlighted alternating items

### 4.4 About / The Studio
- **Headline:** "We don't manage images — we forge them."
- **Photo collage:** 3-image grid (2 portrait + 1 landscape spanning full width)
- **Pull quote:** Blockquote with rust left border
- **Body copy:** 2 paragraphs on origin and reach
- **Badge:** "8 Years redefining personal authority in Southeast Asia"
- **Est.:** 2016, Makati City

### 4.5 Client Showcase
- Horizontally scrollable case study cards
- Cards: 1 wide (450px) + 4 standard (285px)
- Per card: portrait photo, category tag, client name, 1-line result, "Read Case →" link
- Clients featured: Rafael Santos, Isabel Reyes, Marco dela Cruz, Sofia Lim, Adrian Tan

### 4.6 Proof Strip
- 4-column stats grid with hover underline animation
- Stats: ₱2.4B+ Market Value Created · 38 Global Markets · 97% Retention · 120+ Icons Forged

### 4.7 Philosophy
- Full-width dark section (ink background)
- Large italic Playfair quote on intentional personal branding
- Attribution: FORMA Founding Manifesto, Makati City, 2016

### 4.8 Team
- 4-column grid
- Per member: portrait photo, name, role, department cap label
- Team: Alejandro Villanueva (Founder & Chief Strategist), Mia Castillo (Creative Director), David Sy (Head of Media), Lucia Hernandez (Narrative Architect)

### 4.9 CTA / Intake Form
- Split layout: left (copy + urgency signals) · right (form)
- Fields: Full name · Email · Role & company
- Urgency: "Q2 2025 — 4 Spots Remaining"
- Submit behavior: validates email, shows confirmation state for 4 seconds
- Fine print: "By invitation only · Strictly confidential · Response within 48 hrs"

### 4.10 Footer
- 4-column: Brand column + Agency · Services · Contact
- Social links: LinkedIn, Instagram, Twitter/X, Behance
- Copyright: © 2025 FORMA Agency, Inc. · Makati City, Philippines

---

## 5. Interactions & Animations

| Interaction | Behavior |
|-------------|----------|
| Custom cursor | 6px dot (ink) + 32px ring (rust border); ring expands to 50px on hover |
| Scroll reveal | `.rv` (up), `.rvl` (left), `.rvr` (right) — triggered by IntersectionObserver at 10% threshold |
| Staggered delays | `.d1` 0.1s → `.d4` 0.48s |
| Floating card | Hero card floats on 4s sine loop (±7px Y) |
| Nav scroll | Transparent → frosted at scrollY > 60px |
| Photo hover | Scale 1.04–1.05 on all portfolio images |
| Stat hover | Background lightens + rust underline slides in from left |
| Form submit | Valid: green confirmation state for 4s. Invalid: rust border flash for 1.8s |
| Marquee | Continuous 28s linear scroll, duplicated for seamless loop |

---

## 6. Responsive Breakpoints

| Breakpoint | Changes |
|------------|---------|
| ≥ 1600px | Wider horizontal margins (5.5rem) |
| ≤ 1100px | Hero single column (photo panel hidden), 2-col proof grid, 2-col team, 2-col footer |
| ≤ 768px | Nav collapses to burger, reduced margins/padding, single-col footer |

---

## 7. Technical Requirements

- **Stack:** Single-file HTML (HTML + CSS + vanilla JS, no dependencies except Google Fonts)
- **Fonts:** Playfair Display (700, 900, italic variants) · IBM Plex Mono (400, 500) · Epilogue (300, 400, 500) — loaded via Google Fonts
- **Browser support:** Modern evergreen browsers (Chrome, Safari, Firefox, Edge)
- **Performance:** No external JS libraries; IntersectionObserver for scroll triggers; RAF loop for cursor
- **Accessibility:** `aria-hidden` on decorative marquee; semantic HTML5 sections; smooth scroll via CSS + JS

---

## 8. Out of Scope (v1)

- CMS or backend integration
- Real client photography (placeholders used)
- Mobile menu drawer implementation
- Case study detail pages
- Blog or editorial section
- Analytics integration
- Multi-language support

---

## 9. Future Considerations

- Connect intake form to CRM (HubSpot / Notion)
- Add case study pages for each client monograph
- Implement mobile nav drawer
- Add real photography and video content
- A/B test CTA copy and urgency signals
- SEO meta tags and Open Graph implementation
