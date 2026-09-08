---
name: War-Buck Marketing
description: Marketing agency site for local service businesses — paid ads, organic social, and website builds
colors:
  ledger-black: "#000026"
  ledger-black-raised: "#000026"
  ledger-black-raised-2: "#000026"
  ink-hairline: "#48566c"
  cool-paper: "#f3f5f9"
  cool-paper-deep: "#e6eaef"
  white: "#ffffff"
  ink-text: "#10141b"
  ink-text-muted: "#49505c"
  ink-text-faint: "#636974"
  paper-text-on-ink: "#eff2f7"
  paper-text-on-ink-muted: "#9da5b1"
  paper-text-on-ink-faint: "#798496"
  signal-blue: "#2255d5"
  signal-blue-hover: "#1241c1"
  signal-blue-light: "#427afe"
  signal-blue-deep: "#000026"
  hairline: "#d4d8de"
  hairline-strong: "#b2b8c1"
typography:
  display:
    fontFamily: "'Cabinet Grotesk', 'Switzer', sans-serif"
    fontSize: "clamp(2.75rem, 6vw, 5rem)"
    fontWeight: 800
    lineHeight: 1.05
    letterSpacing: "-0.02em"
  headline:
    fontFamily: "'Cabinet Grotesk', 'Switzer', sans-serif"
    fontSize: "clamp(1.75rem, 3.2vw, 2.5rem)"
    fontWeight: 800
    lineHeight: 1.1
    letterSpacing: "-0.02em"
  title:
    fontFamily: "'Cabinet Grotesk', 'Switzer', sans-serif"
    fontSize: "clamp(1.05rem, 1.5vw, 1.25rem)"
    fontWeight: 700
    lineHeight: 1.3
    letterSpacing: "-0.01em"
  body:
    fontFamily: "'Switzer', -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: 1.6
    letterSpacing: "normal"
  label:
    fontFamily: "'Switzer', sans-serif"
    fontSize: "12px"
    fontWeight: 700
    lineHeight: 1.3
    letterSpacing: "0.1em"
rounded:
  sm: "8px"
  md: "14px"
  lg: "26px"
spacing:
  sm: "16px"
  md: "28px"
  lg: "40px"
  xl: "64px"
components:
  button-primary:
    backgroundColor: "{colors.signal-blue}"
    textColor: "{colors.white}"
    rounded: "{rounded.sm}"
    padding: "16px 30px"
  button-primary-hover:
    backgroundColor: "{colors.signal-blue-hover}"
  button-secondary:
    backgroundColor: "transparent"
    textColor: "{colors.ink-text}"
    rounded: "{rounded.sm}"
    padding: "16px 28px"
  button-secondary-hover:
    backgroundColor: "{colors.signal-blue}"
  card-case:
    backgroundColor: "{colors.ledger-black}"
    textColor: "{colors.paper-text-on-ink}"
    rounded: "{rounded.lg}"
    padding: "44px 44px 40px"
  input:
    backgroundColor: "{colors.white}"
    textColor: "{colors.ink-text}"
    rounded: "10px"
    padding: "12px 16px"
  input-focus:
    backgroundColor: "{colors.white}"
---

# Design System: War-Buck Marketing

## 1. Overview

**Creative North Star: "The Operator's Ledger"**

War-Buck Marketing's interface reads like the private ledger of an operator who's actually closing deals, not a SaaS company's marketing deck. The canvas is near-black — Ledger Black (#000026), not a "dark mode" gray — because the brand personality is a serious operator, not a scrappy freelancer and not a faceless corporate SaaS vendor. Against that black, exactly one color is allowed to matter: Signal Blue (#2255d5), used decisively wherever there's a number, a result, or a call to act. Everything else is near-black ink, off-white paper, or quiet gray text — no secondary or tertiary accent colors competing for attention.

This system explicitly rejects the pastel-blue, light-background, icon-in-rounded-box "corporate SaaS" register the site shipped with before its 2026-07-02 redesign. That look reads as generic B2B software; this audience — lawn care, roofing, HVAC, tree service, detailing, and contractor owners evaluating an agency from their phone between jobs — needs to feel "these people know what they're doing," not "here's another tool."

**Key Characteristics:**
- Near-black canvas as the default surface for high-stakes sections (nav, hero, case studies, mobile menu), not just a dark-mode toggle
- One saturated blue (Signal Blue) carries every accent, CTA, and highlighted number — never diluted into a pastel tint
- Cabinet Grotesk (extra-bold, tight tracking) for anything that needs to command attention; Switzer for everything read at length
- Proof-first layout: real client numbers and case-study metrics get the same typographic weight as headlines, because results are the pitch
- Soft, colored (never pure-black) ambient shadows — depth reads as considered, not heavy

## 2. Colors

A two-surface system (near-black "ledger" sections, off-white "paper" sections) with one saturated blue doing all accent work across both. **There are exactly two surfaces — there is no third.** Every dark surface in the system is the same single value; see The One Dark Surface Rule.

### Primary
- **Signal Blue** (#2255d5 / `oklch(50% 0.205 264)`): every CTA, link hover, active state, highlighted metric digit, and form-focus ring. This is the only saturated color in the system.
- **Signal Blue Light** (#427afe / `oklch(61.5% 0.205 264)`): Signal Blue's on-ink counterpart — accents, kickers, and highlighted numbers sitting on the Ledger Black surface, where full-saturation Signal Blue drops to 3.2:1. Measures 5.30:1 on Ledger Black. **It differs from Signal Blue in lightness only** — identical chroma (0.205) and hue (264); see The On-Dark Lightness Rule.
- **Signal Blue Deep** (#000026): retained as a token name (`--accent-deep`, `--accent-deep-2`) but **no longer a distinct colour** — it resolves to Ledger Black like every other dark surface. Kept only so existing call sites keep reading semantically; do not give it a separate value again.

### Neutral
- **Ledger Black** (#000026 / `oklch(12.14% 0.084 264)`): the *only* dark surface — nav (scrolled), hero, `#why`, mobile menu, case-study cards, `#contact`, footer, and `website-design.html`'s `#proof`. Not a neutral gray: it is pure blue (`R=G=0`), which puts it at exactly hue 264, the brand hue.
- **Ledger Black Raised** / **Raised 2** (both #000026): these tokens (`--ink-raised`, `--ink-raised-2`) still exist but hold the **same value** as Ledger Black. The stacked-surface idea was deliberately removed on 2026-09-08 — see The One Dark Surface Rule.
- **Cool Paper** (#f3f5f9 / `oklch(97% 0.006 260)`): the primary light surface for body sections. A true cool off-white, not a warm cream — chroma is tinted toward the brand's own blue hue, not toward warmth.
- **Cool Paper Deep** (#e6eaef): the secondary light surface, used to separate adjacent light sections (e.g. the portfolio section sits on Cool Paper Deep against a Cool Paper page background).
- **Ink Text** (#10141b, 16.93:1) / **Muted** (#49505c, 7.43:1) / **Faint** (#636974, 5.05:1): the three-step text ramp for Cool Paper surfaces. Every step clears 4.5:1 on both Cool Paper and Cool Paper Deep (Faint is tightest at 4.55:1 on Cool Paper Deep).
- **Paper Text on Ink** (#eff2f7, 18.19:1) / **Muted** (#9da5b1, 8.24:1) / **Faint** (#798496, 5.39:1): the corresponding ramp for Ledger Black — never pure white, always a soft paper tone so it doesn't glare against near-black. Ratios measured against #000026; because there is now only one dark surface, each token has exactly one on-ink ratio to satisfy.
- **Hairline** (#d4d8de) / **Hairline Strong** (#b2b8c1): dividers and input borders on light surfaces (FAQ separators, form fields, section rules).

### Named Rules
**The One Signal Rule.** Signal Blue is the only saturated color anywhere in the system. If a new element needs emphasis, it gets Signal Blue, weight, or size — never a second accent hue.

**The Readable Faint Rule.** The faint tier is the bottom of each ramp, not a licence to go lighter. Both faint tokens were re-tuned on 2026-09-07 (`--text-faint` 58%→52% L, `--text-on-ink-faint` 52%→61% L) because they measured 3.9:1 and 3.6:1 — under AA. Any new text color must clear **4.5:1 against every surface it lands on**, measured against the real rendered color, not estimated by eye. Verify before shipping; a lighter gray "for elegance" is the single most common way this system degrades.

**The One Dark Surface Rule.** There is exactly one dark value in this system: #000026. Nav,
hero, `#why`, cards, `#contact`, footers and `#proof` all use it, and `--ink`, `--ink-raised`,
`--ink-raised-2`, `--accent-deep` and `--accent-deep-2` all resolve to it. This replaced five
different darks (#080d16 / #111824 / #1b2433 / #08173d plus a grain overlay on two sections only),
which produced visible seams wherever two of them met — Buck's report was "it should be polished
and one clean color not have these seperations." **Do not reintroduce a raised or stepped dark
surface to make a card read as elevated.** Separation on ink comes from hairlines
(`--ink-line`, `--ink-line-soft`), radius, and spacing — never from a second dark value. If a
future change appears to need one, the seam it creates is the thing being asked for, and the
answer is no.

**The On-Dark Lightness Rule.** Signal Blue Light must differ from Signal Blue in **lightness
only** — same chroma (0.205), same hue (264). It was originally `oklch(74% 0.135 258)`, which was
both desaturated and 6° off-hue, so every on-ink accent read as pale periwinkle while buttons on
light surfaces stayed properly saturated. If this token is ever retuned, move L and nothing else.
The floor is ~61.5% L: below that the `.hero-proof-tag` on ink drops under 4.5:1.

**The Pure-Blue Dark Rule.** The dark surface is constructed as `R=G=0`, which pins it to hue 264 —
the brand hue — at any lightness. To make it lighter or darker, change only the blue channel; the
hue cannot drift. This is why the 2026-09-08 #000033 → #000026 change needed no hue re-check.

**The Warmth-Free Neutral Rule.** Every "white" and "black" in this system is tinted toward the brand's own blue (hue 258–264), never toward cream/warm neutrals. Cool Paper is not off-white-by-default; it's off-white-by-formula.

## 3. Typography

**Display Font:** Cabinet Grotesk (weights 500/700/800), with Switzer, sans-serif fallback
**Body Font:** Switzer (weights 400/500/600/700), with -apple-system, BlinkMacSystemFont, sans-serif fallback

**Character:** Cabinet Grotesk is a rounded-geometric extra-bold — confident and slightly friendly, never sharp/aggressive. Switzer is a clean humanist sans that stays legible and unpretentious at body sizes. The pairing reads as "an operator who's serious but not cold."

### Hierarchy
- **Display** (800, `clamp(2.75rem, 6vw, 5rem)`, line-height 1.05, letter-spacing -0.02em): hero H1s only, always Cabinet Grotesk.
- **Headline** (800, `clamp(1.75rem, 3.2vw, 2.5rem)`, line-height 1.1, letter-spacing -0.02em): section titles (`.section-title`) — the H2 that opens every major page section.
- **Title** (700, `clamp(1.05rem, 1.5vw, 1.25rem)`, line-height 1.3): service/feature card titles (`.svc-title`) — deliberately restrained; this system does not use oversized card headings.
- **Body** (400, 16px, line-height 1.6): default paragraph copy, Switzer, capped conceptually around 65–75ch for readability.
- **Label** (700, 12px, letter-spacing 0.1em, uppercase): form-section labels and the `nav-brand-sub` tagline under the logo — the only uppercase-tracked text in the system, used sparingly and functionally, not as a decorative section eyebrow.

### Named Rules
**The No-Shout Rule.** Display text never exceeds `clamp(2.75rem, 6vw, 5rem)` (~80px). This system was measured down from larger headline sizes site-wide on 2026-07-02 specifically because oversized type read as "shouting" rather than confident — don't push scale back up.

**The Functional Uppercase Rule.** Uppercase, letter-spaced text is reserved for two specific functional roles (nav sub-label, form-section labels) — never used as a decorative kicker above every section heading.

## 4. Elevation

Shadows are soft, warm-tinted-toward-ink (never pure black: `oklch(20% 0.02 260 / alpha)`), and present as ambient depth on floating elements at rest, then intensify on interaction — not purely a hover-triggered effect, but not a heavy, constant drop-shadow either. Ledger Black surfaces themselves (case-study cards, nav, mobile menu) carry no shadow at all; they're full-bleed ink blocks that don't need to "lift." Shadow is reserved for elements that visually float above a surface — chiefly the portfolio site-preview frames.

### Shadow Vocabulary
- **Ambient Small** (`0 2px 10px oklch(20% 0.02 260 / 0.07)`): the lightest touch, for small floating elements.
- **Ambient Medium** (`0 14px 36px oklch(20% 0.02 260 / 0.12)`): the resting state for portfolio site-preview cards (`.site-frame`) — present by default, not just on hover.
- **Ambient Large** (`0 28px 72px oklch(20% 0.02 260 / 0.20)`): the hover/lifted state — `.site-frame` promotes from Medium to Large and translates up 6px on hover, so the card visibly rises toward the viewer.

### Named Rules
**The Ink-Tinted Shadow Rule.** No shadow in this system is pure black. Every shadow is `oklch(20% 0.02 260 / alpha)` — a near-black tinted toward the brand's own hue — so depth reads as part of the same world as the ink surfaces, not a generic CSS default.

## 5. Components

### Buttons
- **Shape:** 8px radius (`--radius-sm`), consistent across primary and secondary.
- **Primary:** Signal Blue background (#2255d5), white text, 700 weight, 16px/30px padding. An inline arrow icon slides right 3px on hover.
- **Hover / Focus:** background steps to Signal Blue Hover (#1241c1) and the button lifts 2px (`translateY(-2px)`); transition is the system's signature ease curve (`cubic-bezier(0.16, 1, 0.3, 1)`).
- **Secondary:** transparent background, 1.5px Hairline Strong border, ink text. On hover, border shifts to Signal Blue and a faint 6%-opacity Signal Blue tint fills the background. An `.on-ink` variant swaps the border/text ramp for the Ledger Black surface (Paper Text on Ink + Signal Blue Light on hover).
- **Large variant:** 17px text, 19px/38px padding — used for the single highest-priority CTA per page (hero, final CTA).

### Cards
- **Case-study card:** Ledger Black background, 26px radius (`--radius-lg`), no shadow — a full-bleed ink block. Contains a small Signal-Blue-Light tag (dot + uppercase label), a large Cabinet Grotesk client name, and a 4-column metrics grid (2-column on mobile) separated by 1px hairlines on an ink-line-soft background, each metric a big Cabinet Grotesk number (accent-highlighted digits in Signal Blue Light) over a small caption.
- **Portfolio preview card (`.site-frame`):** 14px radius (`--radius-md`), Ledger Black background (same value as the section behind it — the shadow, not a lighter fill, is what makes it read as raised), browser-chrome dots header, 16:10 image at `object-position: top`. Carries Ambient Medium shadow at rest, promotes to Ambient Large + 6px lift on hover. This is the system's one "card that behaves like a physical object" — everything else stays flat.

### Inputs / Fields
- **Style:** white background, 1.5px Hairline Strong border, 10px radius, Switzer 15px text.
- **Focus:** border shifts to Signal Blue with a soft 3px Signal-Blue glow ring (`0 0 0 3px oklch(50% 0.205 264 / 0.14)`). This is the one place that overrides the global focus ring below, via specificity.
- **Labels:** every field carries a real `for`/`id` pair (or wraps its input, as the checkbox rows do). Never a bare `<label>` sitting next to an unassociated input — a placeholder is not an accessible name.
- **Checkboxes / radios:** custom-styled 18px squares/circles, Hairline Strong border at rest, fill solid Signal Blue with a white checkmark/dot when checked. The parent label row also gets a Signal Blue border + 6%-tint background when its input is checked.
- **Section label:** small 12.5px uppercase Signal Blue label above each form section (Your Information / About Your Business / Your Marketing) — the input system's one deliberate use of the Functional Uppercase Rule.

### Navigation
- **Style:** fixed, full-width, 18px/40px padding. **Transparent until scrolled** — both the background *and* the bottom border are `transparent` at rest, switching to Ledger Black + a soft ink hairline once `.scrolled` is toggled at `scrollY > 20`. At the top of every page the bar floats directly over the dark hero with no edge at all; the hairline exists only to separate the bar from light content once the page has moved. (Transparent-at-rest added 2026-09-08.)
- **No drop shadow, scrolled or not** — the scrolled background is Ledger Black, the same token as the dark hero/why/footer sections, so over those a shadow reads as an unexplained dark band with a hard 1px edge across the section. The hairline is the separator. (Removed 2026-09-07.)
- **Validating the transparent state:** a DOM-ancestor contrast audit is *wrong* for this bar — it composites the nav against `body` (light Cool Paper) rather than against the dark hero it actually floats over, and reports a false failure for every nav element on every page. Screenshot the nav strip at scroll 0 with the nav's own text forced `color: transparent`, and measure real pixel luminance instead. Current: mean luminance 0.0048 across the 17 pages that carry the bar, worst nav text 4.94:1.
- **Brand lockup:** Cabinet Grotesk wordmark (19px, 800 weight) stacked over a tiny Signal-Blue-Light uppercase tagline (10px, letter-spacing 0.18em) — the nav's only uppercase-label usage.
- **Links:** Paper Text on Ink Muted at rest, brightening to full Paper Text on Ink on hover; no underline, no pill background.
- **Mobile:** collapses to a hamburger under 900px, which opens a full-screen Ledger Black takeover with oversized (32px) Cabinet Grotesk links, each row divided by a soft ink hairline.

### Focus (global)
Every focusable element except form fields gets `:focus-visible { outline: 2px solid Signal Blue; outline-offset: 2px; box-shadow: 0 0 0 2px white; }`. The accent ring carries the contrast on light surfaces (5.8:1) and the white halo carries it on ink (17:1), so one ring works everywhere without enumerating which sections are dark — `#proof` is light on index.html and dark on website-design.html, so a selector list would be wrong. Chrome's default ring (#005fcc) is not used here: it measures 3.41:1 on Ledger Black — technically over the 3:1 non-text minimum since the surface darkened on 2026-09-08, but with almost no margin, against 20.43:1 for the white halo. (Before that change it measured 2.9:1 and genuinely failed; the custom ring is now kept for the margin, not because the default fails outright.)

### Grain (de-banding layer)
`#hero` carries a `::after` tiled with `images/grain.png` (128px mean-neutral noise) in `mix-blend-mode: overlay`, over an `isolation: isolate` parent. The hero glow spans only ~26 of 256 blue levels, so 8-bit quantisation leaves visible contour rings on desktop panels (phones hide it via 3x DPR + panel dithering). The grain dithers the ramp. Mid-grey under `overlay` is mean-neutral, so flat areas keep their exact color and no seam appears against the adjacent flat ink. `images/hero-glow.png` also has dither baked into its alpha. Don't "clean up" either asset.

**`#contact` no longer carries grain or a glow** (removed 2026-09-08). Its background is now flat Ledger Black, identical to the footer beneath it, so the two run together with nothing to band and no seam to hide. Re-adding a glow there would reintroduce both problems. **Verify banding by measuring, not by eye:** scan a vertical line of pixels through the gradient and record the longest run of identical blue values. The hero currently sits at a 6px worst flat run. When re-checking against a past figure, re-measure the old state too — a recorded number from a different sampling method is not comparable.

### FAQ Accordion (signature component)
Hairline-divided list (`.faq-item`), each question a full-width button that turns Signal Blue and rotates its trailing icon when open; the answer panel animates open via `grid-template-rows` (0fr → 1fr) rather than height/max-height, keeping the transition smooth without a fixed pixel guess.

## 6. Do's and Don'ts

### Do:
- **Do** keep Signal Blue (#2255d5) as the only saturated accent color anywhere on the site, including in any new marketing assets (social cards, ads, email headers).
- **Do** tint every "neutral" black/white toward the brand's own hue (258–264°) rather than defaulting to pure black/white or a warm cream.
- **Do** lead with concrete numbers (client counts, days-to-result, revenue figures) at full typographic weight — proof is the design, not a footnote.
- **Do** use the ink-tinted shadow formula (`oklch(20% 0.02 260 / alpha)`) for any new shadow, never a flat `rgba(0,0,0,...)`.
- **Do** size every grid track as `minmax(0, 1fr)`, never bare `1fr`. Bare `1fr` means `minmax(auto, 1fr)`, so children can't shrink below min-content and push past the viewport in a narrow band of widths — this has caused a stray horizontal scrollbar on this site twice.
- **Do** verify contrast against the real rendered color before shipping a new text or border color, and disable CSS transitions first — reading a computed style mid-transition returns the pre-transition value and produces false results.
- **Do** measure by pixel, not by DOM, for anything whose background comes from a gradient, an image, or a `position: fixed` ancestor — the fixed nav and the gradient-scrim image labels (`.proof-strip-label`, `.demo-card-label`) both report false contrast failures under an ancestor walk, because `getComputedStyle().backgroundColor` cannot see what is actually behind them.
- **Do** render a 4–5 step ladder on the real page when changing an existing colour's lightness or saturation, and pick from that — injected via a Playwright `!important` override, no file edits. Guessing a single value cost three rounds on the accent blue; the ladder settled the surface darkening in one.
- **Do** cap display type at `clamp(2.75rem, 6vw, 5rem)` — this was deliberately reduced site-wide on 2026-07-02 after oversized headings read as "shouting."

### Don't:
- **Don't** revert to the pre-2026-07-02 look: light blue/white pastel gradients, rounded icon-in-a-box service cards, pastel badges, or a tiny uppercase tracked kicker above every section. That register reads as generic corporate SaaS, which is explicitly the wrong register for this audience.
- **Don't** introduce a second accent color. If something needs more emphasis than Signal Blue gives it, increase weight or size instead.
- **Don't** use `border-left`/`border-right` as a colored accent stripe on cards or list items.
- **Don't** apply `background-clip: text` gradient text anywhere — emphasis comes from weight/size/color, never a text gradient.
- **Don't** add uppercase tracked eyebrows above every section heading. Uppercase-tracked text is reserved for the nav tagline and form-section labels only (see The Functional Uppercase Rule).
- **Don't** introduce a second dark surface value to create elevation, separation, or a "raised" card. See The One Dark Surface Rule — this was explicitly undone once already and the seams were the reason.
- **Don't** change Signal Blue Light's chroma or hue when adjusting it, only its lightness (The On-Dark Lightness Rule).
- **Don't** put a drop shadow on the fixed nav. Its background is the same token as the dark sections, so the shadow becomes a floating dark band across them rather than a bar edge.
- **Don't** give Ledger Black surfaces (case-cards, nav, mobile menu) a drop shadow — they're flat, full-bleed ink blocks by design; shadow is reserved for elements that should read as physically floating (portfolio preview cards).
