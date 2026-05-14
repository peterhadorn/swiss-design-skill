---
name: swiss-design
description: Build websites in the Swiss / International Typographic Style — Müller-Brockmann grids, disciplined typography, ink-on-paper restraint, and the modern agency-grade idioms (arrow-in-circle CTAs, eyebrow tags, type-as-architecture, ambient parallax, Lenis smooth scroll, custom cursor, oklch color, dark mode, view transitions) that make a Swiss-style site memorable without being noisy. Use when the brief calls for "Swiss," "minimalist," "editorial," "premium-conservative," "agency-clean," or references Mobiliar / seoagentur.de / Doppio / Stink Studios / favorit.studio / eseagency.ch.
---

# Skill: Swiss Design (International Typographic Style for the Web)

## 1. What this skill produces

A website that **feels Swiss before any word is read**: orderly, generous, left-aligned, restrained, confident. Quality through structure and typography, not through effects. The output is **agency-grade** and looks deliberately built — not generated. It should be impossible to mistake the result for "another modern AI-template landing page."

This skill is the descendant of Müller-Brockmann, Ruder, and Hofmann translated into 2026 web idioms used by award-winning Swiss and Swiss-influenced agencies (Mobiliar, seoagentur.de, Doppio, favorit.studio, eseagency.ch, Stink Studios).

**Use this skill when the brief calls for:** "Swiss style," "International Typographic Style," "editorial-clean," "minimalist-premium," "agency-grade," "Mobiliar-conservative-cousin," "Notion/Linear sensibility but more disciplined." Pair with a brand-specific style file when the project has its own palette and voice.

---

## 2. The Swiss canon — what we are translating to web

The International Typographic Style emerged in Basel and Zurich in the late 1940s. Its core principles, distilled from Müller-Brockmann's *Grid Systems* and Ruder's *Typography*, are:

- **Asymmetric balance on a strict grid.** Symmetry is for ceremony; structure is for communication.
- **Sans-serif, Swiss neo-grotesque.** Akzidenz-Grotesk, Helvetica, Univers — and their modern descendants.
- **Flush-left, ragged-right.** Readability over decorative justification.
- **Generous, deliberate whitespace.** Whitespace is *active* — it carries information about hierarchy and rest.
- **Objective photography over decoration.** When images appear, they document; they do not embellish.
- **Color is functional.** A single deliberate accent over neutral substrate.
- **Type carries the design.** Decoration is forbidden; hierarchy comes from scale, weight, and spacing.

These are not aesthetic preferences. They are an information design discipline.

---

## 3. Absolute negative constraints (BANNED)

A design that contains any of the following has failed:

### Banned typography
- **Inter, Roboto, Open Sans, Arial, system-ui, Lato, Poppins.** The AI-default tells. Use proper Swiss neo-grotesque or modern descendants (see §5).
- Decorative serif as body type. Editorial serif is permitted *only* for one display-scale moment per page (a hero, a pull quote).
- Monospace as a "techy aesthetic" shortcut. Monospace is for code, metadata, numerals — never as primary headline type unless the brand explicitly demands it.
- More than three weights across the entire site (typically Regular, Medium, Bold).
- More than two type families (one neo-grotesque + at most one editorial serif for accent moments).

### Banned color
- **Purple/blue gradients.** The single most common AI-design fingerprint. Never appears in a Swiss design.
- Three-stop gradients in any direction (the "wine→coral→wine" ribbon energy).
- Multiple accent colors. *One* accent. Ever.
- Saturation above 80% on supporting accents.
- `#000000` body type or `#FFFFFF` background as defaults — use ink (`#111` or `#1A1A1A`) on warm/neutral paper (`#F7F6F3`, `#FAFAF7`, or pure `#FFFFFF` when the brand demands it).
- Dark sections randomly inserted into a light page (the "let's add visual variety" anti-pattern). Commit to the substrate.

### Banned layout
- Centered hero blocks. Swiss design is **left-aligned, ragged-right** by canon.
- Three equal cards in a row as a feature section. (Use a 2-column zig-zag, asymmetric grid, or single-column flow.)
- Edge-to-edge sticky navbars with no breathing room.
- `100vh` (use `100dvh` to prevent iOS Safari viewport jump).
- Forced equal-height cards via flexbox when content varies.
- Symmetrical vertical padding on sections (bottom should usually be optically slightly larger than top).
- Two-column "text + image" grids for *every* content section. Default is single-column flow with images embedded inline.
- Width constraints on text elements (`max-width` on `<p>`, `<h2>`, etc.). Width belongs on the *container*; text fills it.

### Banned components / decoration
- Glassmorphism, neumorphism, claymorphism (anything *-morphism beyond restrained navbar blur).
- Generic thin-stroke icon libraries (Lucide / Feather / Heroicons stock). Use Phosphor (Bold/Fill), Radix UI Icons, or hand-drawn SVG primitives standardized to one stroke width.
- Drop shadows above `0.05` opacity. Heavy `shadow-md` / `shadow-lg`.
- Rounded-full pill containers for cards or large blocks. **Round shapes (pill, circle) are reserved for action items only** — primary CTAs, button-arrow wrappers, interactive chips. Eyebrows, tags, badges, and other static labels stay flat (no frame, or square corners if filled). A pill-bordered eyebrow reads like a tiny button and competes with the actual CTA.
- `rounded-3xl` on everything. Vary radius — softer on outer containers, tighter on inner elements.
- Decorative icons-with-rounded-corners above every heading. (The templated AI-tell.)
- Emojis. Anywhere. Including code, alt text, copy.

### Banned 2026 AI-template fingerprints
- **shadcn/ui defaults verbatim** — `bg-zinc-950` dark cards with `border-zinc-800`, the "AI startup" aesthetic. Restyle if you must use shadcn primitives.
- **Tailwind UI hero patterns** — centered hero with radial-gradient blur (the "Spotlight" template). Instantly readable as template.
- **Vercel deploy template aesthetic** — Inter + linear gradient mesh + dark glass card.
- **Linear / Cal.com glass header** — `backdrop-filter: blur(16px); background: rgba(...,0.6)` outside one restrained nav use.
- **Bento grid as default layout** — 3×2 cards-of-varying-sizes is now an AI tell. Use only when content genuinely demands it.

### Banned motion
- Default `linear` or `ease-in-out` transitions. Slop tells.
- `window.addEventListener('scroll')` for entry animations. Use CSS `animation-timeline: view()` (preferred) or `IntersectionObserver` (fallback). See §8 pattern #6.
- Animations that run continuously without dampening (rotating logos, pulsing CTAs, blinking arrows).
- Mounting all elements at once. Use staggered reveals.
- **Ignoring `prefers-reduced-motion`.** Every animation must have a reduced-motion override (see §8).

### Banned copy in design output
- AI-marketing clichés: "Elevate," "Seamless," "Unleash," "Next-Gen," "Game-changer," "Delve," "Empower," "Revolutionize," "Transform your business."
- Filler placeholders: "Lorem Ipsum," "John Doe," "Acme Corp."
- Vague promises ("powerful tools," "great results"). Specific or silent.

---

## 4. Grid system (Müller-Brockmann web)

### Container
- Outer container: **max-width `1200–1440px`**, centered with auto margins.
- Side gutters: **`clamp(1rem, 5vw, 2.5rem)`**.
- Inner content (text-heavy): typically nested in a `max-width: 720–860px` reading column, **left-aligned within the outer container** (not centered).

### Column grid
- 12-column grid is the Swiss default.
- Use **CSS Grid**, not flexbox percentage math.
- Gutters between columns: 16–32px depending on density.
- **Asymmetric occupation.** Headline often takes columns 1–7; body takes 1–6; supporting visual takes 8–12. Never default to 50/50.

### Vertical rhythm
- Define a **modular spacing scale** as CSS variables:
  ```css
  --space-xs: 0.5rem;   /* 8px */
  --space-sm: 1rem;     /* 16px */
  --space-md: 1.5rem;   /* 24px */
  --space-lg: 2.5rem;   /* 40px */
  --space-xl: 4rem;     /* 64px */
  --space-2xl: 6rem;    /* 96px */
  --space-3xl: 8rem;    /* 128px */
  --space-4xl: 12rem;   /* 192px */
  ```
- Section spacing: **`--space-3xl` to `--space-4xl`** between major sections. Generous. The page should feel like a Swiss publication, not a feed.
- Within a section: every gap (margin, padding, grid `gap`) comes from the scale. **Never raw pixel values**.
- Optical bias: bottom padding of a section is usually slightly larger than top (e.g., `padding: var(--space-3xl) 0 var(--space-4xl)`).

### Hairline rules
- Section dividers, table rows, list separators: `1px solid var(--rule)` — defined in §6 as `oklch(92% 0.005 90)` (≈`#EAEAEA`). These hairlines are a Swiss-design signature and replace heavy borders.

---

## 5. Typography

### Font selection
**Sans-serif (primary):** A Swiss neo-grotesque. In order of preference:
- **Suisse Int'l** (commercial — Swiss Typefaces, ideal for Swiss brands)
- **Neue Haas Grotesk** (Helvetica's serious sibling)
- **Helvetica Neue** (system-available fallback, acceptable but tired)
- **Söhne** (Klim, modern Swiss-inspired)
- **GT America** (Grilli Type, modern American grotesk with Swiss DNA)
- Open-source fallbacks: **Inter Tight** (yes, Inter Tight, *not* default Inter — the tighter cut with proper grotesk character), **Geist Sans**, **Switzer**

**Editorial serif (accent only):** For one display-scale moment per page (hero pull, large quote). Options: Lyon Text, Newsreader, Instrument Serif, PP Editorial New. Apply tight tracking (`-0.02em` to `-0.04em`) and tight line-height (`1.05–1.1`).

**Monospace (data only):** Geist Mono, JetBrains Mono, IBM Plex Mono. For numerals in tables, code, metadata badges. Never as primary type.

### Type scale
Use **fluid `clamp()`** so type breathes responsively:
```css
--text-xs:   clamp(0.75rem,  0.7rem  + 0.2vw, 0.875rem);  /* metadata, eyebrows */
--text-sm:   clamp(0.875rem, 0.85rem + 0.2vw, 1rem);
--text-base: clamp(1rem,     0.95rem + 0.25vw, 1.125rem); /* body */
--text-lg:   clamp(1.125rem, 1.05rem + 0.4vw, 1.375rem);
--text-xl:   clamp(1.375rem, 1.25rem + 0.6vw, 1.75rem);   /* H4 */
--text-2xl:  clamp(1.75rem,  1.5rem  + 1.2vw, 2.5rem);    /* H3 */
--text-3xl:  clamp(2.25rem,  1.8rem  + 2.2vw, 3.75rem);   /* H2 */
--text-4xl:  clamp(3rem,     2.2rem  + 3.5vw, 5.5rem);    /* H1 */
--text-display: clamp(4rem,  2.5rem  + 7vw,   10rem);     /* viewport-bleeding hero */
```

### Hierarchy via *type*, not decoration
- Headlines: tight tracking (`-0.02em` to `-0.04em`), tight leading (`1.05–1.15`).
- Body: line-height **`1.55–1.7`**, letter-spacing `0`, max **65–75 characters per line**.
- Eyebrow tags: `text-xs`, **uppercase**, `letter-spacing: 0.18em–0.22em`. **No frame by default** — just the typographic styling identifies them. If you must frame, use a small **square** filled chip (filled bg, no border, square corners). Never pill-bordered — that reads as a button and competes with the actual CTA. Always above H1/H2 to set rhythm.
- Numerals in data: enable tabular figures (`font-variant-numeric: tabular-nums`).
- All-caps ONLY for eyebrows, micro-labels, and metadata. Never for body or H1/H2.
- Use **medium (500)** weight more than people expect — it's the workhorse weight in Swiss design (regular reads thin, bold reads heavy; medium is the editorial sweet spot).
- Fix orphans with `text-wrap: balance` (headlines) and `text-wrap: pretty` (body).

### Baseline CSS (apply globally before any component)
```css
html {
  font-optical-sizing: auto;        /* enables opsz axis in variable fonts */
  text-rendering: optimizeLegibility;
  -webkit-text-size-adjust: 100%;
  hanging-punctuation: first last allow-end;  /* Safari today; progressive */
}
body {
  font-feature-settings: "kern" 1, "liga" 1, "calt" 1;
}
h1, h2, h3, h4 {
  text-wrap: balance;
  font-feature-settings: "kern" 1, "liga" 1;
}
p, li, figcaption, blockquote { text-wrap: pretty; }
```

**Font loading — `font-display: optional`** — never FOUT-flash. With `optional`, the browser swaps the custom font only if it loaded in the first ~100ms; otherwise the page renders in fallback and stays that way for the session. Premium Swiss-agency discipline:
```css
@font-face {
  font-family: 'Suisse Int\'l';
  src: url('SuisseIntl-Variable.woff2') format('woff2-variations');
  font-weight: 100 900;
  font-display: optional;
}
```
Pair the fallback stack to match metrics (`size-adjust`, `ascent-override`, `descent-override`) so any swap is invisible.

**Variable font intermediate weights** — variable fonts allow sub-step precision:
```css
h2           { font-weight: 450; }   /* between Regular and Medium — very Swiss */
.eyebrow     { font-weight: 520; }
.stat-label  { font-weight: 480; }
```

**OpenType features** — Suisse Int'l, GT America, Söhne all carry alternates:
```css
.headline-alt  { font-feature-settings: "ss01" 1; }  /* alt a, g forms */
.body-humanist { font-variant-numeric: oldstyle-nums; }
```

**Hyphenation** — Swiss print tradition. Web supports it natively. Set regional `lang` on the root: `<html lang="de-CH">` (or `fr-CH`, `it-CH`). The `:lang()` pseudo-class inherits through the DOM, so inline `<section lang="fr-CH">` switches correctly:
```css
:lang(de), :lang(de-CH) { hyphens: auto; hyphenate-limit-chars: 8 4 3; }
:lang(fr), :lang(fr-CH) { hyphens: auto; hyphenate-limit-chars: 10 4 3; }
:lang(it), :lang(it-CH) { hyphens: auto; hyphenate-limit-chars: 8 3 3; }
h1, h2, h3, .eyebrow    { hyphens: none; }  /* never on display type */
```

### Color of type
- Body: **off-black**, never `#000`. Use `#111`, `#1A1A1A`, or `#2F3437`.
- Muted/secondary: a single neutral gray (warm-tinted if substrate is warm, cool if substrate is cool — *never both*). e.g. `#787774` on warm bone paper.
- Headlines: same off-black as body unless the brand explicitly uses an accent for display type.

---

## 6. Color — ink-on-paper philosophy

A Swiss design has at most **four colors**:

1. **Paper** — the substrate. `#FFFFFF`, `#FAFAF7`, `#F7F6F3`, or `#F4F4F0`. Warm-leaning off-white reads more print/Swiss; pure white reads more SaaS-clinical. Pick deliberately.
2. **Ink** — body and headline color. `#111`, `#1A1A1A`, or `#2F3437`. Never `#000`.
3. **Rule** — hairline gray. `#EAEAEA`, `#E5E5E2`, or `rgba(0,0,0,0.06)`.
4. **Accent** — exactly **one**. Used for CTAs, links, the hero word the page wants you to remember, the active nav state. Saturation < 80%. Common Swiss-agency choices: deep red (Mobiliar tradition), aviation red (`#E61919`), wine, deep blue (`#0033A0`), forest green. Pick one and use it with violence.

### Preferred color definition: `oklch()`
`oklch()` is perceptually uniform — the closest CSS equivalent to Pantone precision. Define all four colors in oklch:
```css
:root {
  --paper:  oklch(98% 0.005 90);    /* warm off-white */
  --ink:    oklch(15% 0.010 260);   /* near-black, cool undertone */
  --rule:   oklch(92% 0.005 90);    /* hairline gray */
  --accent: oklch(48% 0.180 25);    /* deep red — Mobiliar-adjacent */
}
```
Use `color-mix(in oklab, ...)` for tints instead of adding new variables:
```css
.card:hover { background: color-mix(in oklab, var(--accent) 6%, var(--paper)); }
```

### Dark mode
Swiss dark mode is not CSS `invert`. It is a deliberate substrate swap — dark ink on dark paper. Grain blend mode flips from `multiply` to `screen`.

Required `<head>` meta — without it, browser chrome (scrollbars, root background) stays light even when CSS switches:
```html
<meta name="color-scheme" content="light dark">
```

Swiss-themed thin scrollbars (works in both schemes):
```css
:root {
  scrollbar-color: var(--rule) var(--paper);
  scrollbar-width: thin;
}
```

```css
@media (prefers-color-scheme: dark) {
  :root {
    --paper:  oklch(12% 0.010 260);   /* dark substrate, not #000 */
    --ink:    oklch(94% 0.005 90);    /* warm off-white, not #fff */
    --rule:   oklch(20% 0.010 260);
    /* --accent stays same hue; optionally bump lightness +5% */
  }
  .grain::before  { mix-blend-mode: screen; opacity: 0.02; }
  .ambient        { opacity: 0.03; }
}
```

### Brand variant: when the project has multiple brand colors
If the brand has two related shades (e.g., a deep and bright variant of the same hue), permit:
- Brand-deep used for primary type accents, dividers, the mark.
- Brand-bright used for hover states, active CTA, the single high-contrast moment.
- They must be from the same hue family. Three-color brand systems break this skill — drop one or use it only on the logo.

### Texture, not gradients
- A subtle **3% film-grain noise overlay** as a fixed background or section background is permitted — gives flat color physical-paper texture. SVG noise filter is preferred (one element, GPU-cheap).
- **Single-color radial light** at very low opacity (`opacity: 0.02–0.04`) as a `position: fixed; pointer-events: none` ambient layer is permitted as the "parallax" unifier (see §8 pattern #10).
- Linear gradients, mesh gradients, animated gradients: banned.

---

## 7. Layout patterns

### Hero — two modes only

**Mode A — Typographic hero (no image).**
- Big left-aligned headline (use `--text-display` or `--text-4xl`) over paper.
- Subhead at `--text-lg` or `--text-xl`, max 2 lines, generous line-height.
- One primary CTA (arrow-in-circle pill, see §9), optional one secondary text link.
- Eyebrow tag above the H1 (uppercase micro-label, e.g., "WEB DESIGN AGENTUR").
- Optional: a single ambient layer behind (radial light, film grain, or subtle structural numerals like a section counter "01 / 06" in the corner).

**Mode B — Typographic hero with right-column image.**
- Same left-side structure as Mode A.
- Right column (cols 8–12 of a 12-grid) holds **one** considered image. Never stock-shaped (no smiling-team-handshake stock). Real portrait, real product screenshot, real document, or considered illustration.
- Image is asymmetric: bleeds intentionally to one edge, breaks the grid by ~10–20%, or sits inside a nested-bezel frame.
- Mobile: image stacks below text, full width, generous top margin.

### Section types
- **Editorial flow:** single column, max 720–860px text width within the outer container, left-aligned. Body text fills the column; supporting visuals (mockups, diagrams) embed inline at full column width or float right at ~45% with proper text-wrap.
- **Asymmetric duo:** two columns, one ~7 grid cols, the other ~5. Never 50/50.
- **Stat row:** 2–4 large numerals (`--text-3xl` to `--text-4xl`) with small uppercase labels below — Swiss data-display pattern. Hairline divider between each.
- **Card grid:** 2 or 4 cards (never 3 unless the content is genuinely categorical-three). Each card: hairline border, generous padding (`--space-md` minimum), one accent moment (eyebrow, arrow, number).
- **Comparison / pricing:** column-aligned baselines across all columns (titles, prices, feature-list-start, CTAs all at the same vertical position).
- **Horizontal work carousel:** for portfolio / project showcases. Scroll-snap, hidden scrollbar, full touch support. Integrates with Lenis automatically:
  ```css
  .work-carousel {
    display: flex; overflow-x: auto;
    scroll-snap-type: x mandatory;
    scroll-padding-inline: clamp(1rem, 5vw, 2.5rem);  /* matches §4 container gutters */
    gap: var(--space-md);
    scrollbar-width: none;
  }
  .work-carousel::-webkit-scrollbar { display: none; }
  .work-carousel > * {
    scroll-snap-align: start;
    flex: 0 0 clamp(280px, 45vw, 640px);
  }
  ```
- **Pull quote:** Swiss editorial signature. Italic editorial serif at display size, hairline above and below, generous block padding:
  ```css
  .pullquote {
    font-family: var(--font-serif);
    font-size: var(--text-3xl);
    line-height: 1.1; letter-spacing: -0.02em;
    font-style: italic;
    text-wrap: balance;
    border-block: 1px solid var(--rule);
    padding-block: var(--space-lg);
    margin-block: var(--space-xl);
  }
  .pullquote cite {
    display: block; margin-top: var(--space-md);
    font-family: var(--font-sans); font-style: normal;
    font-size: var(--text-xs); text-transform: uppercase;
    letter-spacing: 0.18em;
  }
  ```

### Section counters — "01 / 06" in the corner
Pattern referenced in §7 hero options. Native CSS counters, no JS:
```css
body { counter-reset: total 6 section; }    /* set total per page */
.section { counter-increment: section; position: relative; }
.section::before {
  content: counter(section, decimal-leading-zero) ' / '
           counter(total,   decimal-leading-zero);
  position: absolute;
  top: var(--space-md); right: var(--space-md);
  font-size: var(--text-xs);
  letter-spacing: 0.18em;
  font-variant-numeric: tabular-nums;
  color: color-mix(in oklab, var(--ink) 60%, transparent);
}
```

### Footer
- Multi-column with hairline rules between columns (Doppio idiom).
- Top row: brand mark + tagline + primary nav columns (3–4 columns, label uppercase eyebrow + flush-left links).
- Bottom row: copyright, legal links, optional locale switcher, optional small line about the technology / studio that built it.
- Subtle: total content has more whitespace than expected. The footer breathes.

---

## 8. The 13 patterns that produce "Swiss with wow"

These are the structural-typography moments that elevate Swiss restraint into agency-grade memorability. Use **2–3 per page maximum** — moments are special because they are rare.

**`prefers-reduced-motion` is mandatory on every animation in this section:**
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
  .ambient { animation: none; }
}
```

### 1. Type-as-architecture
A viewport-bleeding headline at `clamp(4rem, 10vw, 12rem)`, ultra-tight tracking, leading 0.9. Words become structural elements. Used for hero, manifesto sections, transitional dividers between content blocks.

### 2. Arrow-in-circle CTA
The signature Swiss-agency idiom. A pill-shaped button with the arrow nested in **its own circular wrapper** at the right inner edge:
```html
<a class="cta">
  <span>Unverbindliche Beratung buchen</span>
  <span class="arrow-circle"><svg>↗</svg></span>
</a>
```
- Outer: `border-radius: 9999px`, padding `0.75rem 0.75rem 0.75rem 1.5rem` (less right padding because of the arrow circle), background `var(--accent)` or `var(--ink)`.
- Arrow circle: `width: 2rem; height: 2rem; border-radius: 50%; background: rgba(255,255,255,0.12);`.
- On hover: arrow translates `4px` right and rotates `45deg` simultaneously, cubic-bezier `(0.32, 0.72, 0, 1)` over 400ms.

### 3. Eyebrow tags
`text-xs`, uppercase, `letter-spacing: 0.18em–0.22em`, **no frame by default**. If filled, use a small **square** chip (filled bg, no border, square corners) — never a pill. Round shapes are reserved for action items (CTAs, button-arrows); a pill-bordered eyebrow reads like a tiny button and competes with the actual CTA. Always above H1/H2 to set rhythm. Use across the whole site consistently.

### 4. Custom cubic-bezier motion
Default transitions are slop. All transitions use one of:
- `cubic-bezier(0.32, 0.72, 0, 1)` — for translate/scale (springy, premium feel)
- `cubic-bezier(0.16, 1, 0.3, 1)` — for opacity fades (soft)
Durations: 400ms (UI), 600–800ms (entry reveals).

### 5. Subtle film grain
SVG noise at 3% opacity overlaid on the page (or specific sections) gives flat color physical-paper texture. One element, GPU-cheap, huge perceptual upgrade:
```css
.grain::before {
  content: ''; position: fixed; inset: 0; pointer-events: none; z-index: 1;
  background-image: url("data:image/svg+xml,...noise.svg");
  opacity: 0.03; mix-blend-mode: multiply;
}
```

### 6. Entry reveals — two techniques

**Preferred: CSS scroll-driven** (Chrome 115+ / Safari 26+, runs off-thread):
```css
@keyframes reveal-up {
  from { opacity: 0; transform: translateY(12px); }
  to   { opacity: 1; transform: none; }
}
.section-child {
  animation: reveal-up linear both;
  animation-timeline: view();
  /* Stagger via per-element range offsets — animation-delay does NOT work
     with view() timelines (delay is interpreted as scroll-progress, not time). */
  animation-range:
    entry calc(var(--i, 0) * 8%)
    entry calc(60% + var(--i, 0) * 8%);
}
```

**Agency-grade upgrade: line-masking** — lines slide from behind a mask, like letterpress. No fade, pure geometric motion:
```css
.reveal-line          { overflow: hidden; display: block; }
.reveal-line span     {
  display: block;
  transform: translateY(110%);
  transition: transform 700ms cubic-bezier(0.32,0.72,0,1)
              calc(var(--i, 0) * 100ms);
}
.is-visible .reveal-line span { transform: translateY(0); }
```

**Fallback: IntersectionObserver** (Firefox / progressive enhancement):
```js
const io = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('is-visible') })
}, { threshold: 0.1 })
document.querySelectorAll('[data-reveal]').forEach(el => io.observe(el))
```

Stagger index via `style="--i: <n>"` on each child. Use CSS scroll-driven on supported browsers, IntersectionObserver as `@supports not (animation-timeline: view())` fallback.

### 7. Disciplined asymmetry
The grid is rigid; one element per section deliberately breaks it — a numeral overflows the right margin, a heading bleeds left into the gutter, an image overlaps two columns and the next section. **One break per section, not three.** The break should communicate the section's content (not just decorate).

### 8. Macro-whitespace between sections
`--space-3xl` to `--space-4xl` (96–192px) between major sections. The page reads like a publication, not a feed. This single rule delivers the "calm" that AI-generated sites lack.

### 9. Single accent used with violence
The brand's one accent appears: in CTAs, in active nav, in the one hero word the page is built around, in the link underline. **Nowhere else.** Section headers are ink. Hairlines are gray. Body is ink. The accent's rarity is what makes it powerful.

### 10. Ambient parallax layer (the unifier)
A single fixed-position element behind the page with a low-opacity radial light in the brand accent color. Sections sit on top with opaque/semi-transparent backgrounds (paper at 96% opacity). The ambient layer peeks through gaps between sections, slowly drifts via a 30–60s CSS animation, and unifies the entire site. **One layer. One color. Slow. Never on top of content.**
```css
.ambient {
  position: fixed; inset: 0; pointer-events: none; z-index: 0;
  background: radial-gradient(circle at 30% 40%,
    color-mix(in oklab, var(--accent) 100%, transparent) 0%,
    transparent 60%);
  opacity: 0.04;
  animation: ambient-drift 45s ease-in-out infinite alternate;
}
@keyframes ambient-drift {
  to { transform: translate(8vw, -6vh) scale(1.1); }
}
```

### 11. Smooth scroll (Lenis)
Every premium Swiss site uses smooth scroll — it makes the page feel like a publication being leafed through, not a feed being dragged. Install Lenis (see §13 step 0). Key settings:

| Setting | Value | Why |
|---------|-------|-----|
| `lerp` | `0.08` | Deliberate, Swiss — not bouncy |
| `duration` | `1.2` | Slightly slower than default feels considered |
| `easing` | default | Lenis's built-in is already premium |

Pair with GSAP ScrollTrigger when pinning sections:
```js
lenis.on('scroll', ScrollTrigger.update)
gsap.ticker.add((time) => { lenis.raf(time * 1000) })
gsap.ticker.lagSmoothing(0)
```

### 12. Custom cursor
A 6–8px accent-colored dot that follows with slight lag signals craftsmanship before any scroll. Expands into a ring on interactive elements:
```css
body { cursor: none; }
input, textarea, [contenteditable] { cursor: text; }   /* preserve I-beam */

.cursor {
  position: fixed; top: 0; left: 0;
  width: 8px; height: 8px; border-radius: 50%;
  background: var(--accent);
  pointer-events: none; z-index: 9999;
  opacity: 0;                                         /* hide until first move */
  transition: opacity 200ms,
              width 200ms cubic-bezier(0.32,0.72,0,1),
              height 200ms cubic-bezier(0.32,0.72,0,1),
              background 200ms;
}
.cursor.is-active      { opacity: 1; }
.cursor.on-interactive {
  width: 32px; height: 32px;
  background: transparent; border: 1px solid var(--accent);
}
@media (hover: none) {
  body { cursor: auto; }
  .cursor { display: none; }
}
```
```js
const cursor = document.querySelector('.cursor')
let pending = false, lastX = 0, lastY = 0

document.addEventListener('mousemove', ({ clientX, clientY }) => {
  lastX = clientX; lastY = clientY
  if (pending) return
  pending = true
  // Throttle to rAF — mousemove can fire 1000+/sec; one DOM write per frame is enough.
  requestAnimationFrame(() => {
    cursor.style.translate =
      `${lastX - cursor.offsetWidth / 2}px ${lastY - cursor.offsetHeight / 2}px`
    if (!cursor.classList.contains('is-active')) cursor.classList.add('is-active')
    pending = false
  })
})

document.querySelectorAll('a, button').forEach(el => {
  el.addEventListener('mouseenter', () => cursor.classList.add('on-interactive'))
  el.addEventListener('mouseleave', () => cursor.classList.remove('on-interactive'))
})
```

### 13. View Transitions API
For multi-page and SPA navigation. Adds a deliberate, Swiss-paced fade-slide between pages (Chrome 111+):
```css
@view-transition { navigation: auto; }

::view-transition-old(root) {
  animation: vt-out 300ms cubic-bezier(0.16,1,0.3,1) forwards;
}
::view-transition-new(root) {
  animation: vt-in  300ms cubic-bezier(0.16,1,0.3,1) forwards;
}
@keyframes vt-out { to   { opacity: 0; transform: translateY(-6px); } }
@keyframes vt-in  { from { opacity: 0; transform: translateY(6px);  } }
```
For named transitions (hero image persisting across pages), add `view-transition-name: hero-image` to the shared element — the browser morphs it automatically.

---

## 9. Components

### Buttons
- **Primary:** arrow-in-circle pill (see §8.2).
- **Secondary:** text link with **animated underline** that grows from left:
  ```css
  .link { background-image: linear-gradient(currentColor, currentColor);
          background-size: 0 1px; background-repeat: no-repeat;
          background-position: 0 100%;
          transition: background-size 400ms cubic-bezier(0.32,0.72,0,1); }
  .link:hover { background-size: 100% 1px; }
  ```
- Never use `:hover { transform: scale(1.05) }` on buttons. Slop tell.

### Forms (Mobiliar pattern)
- Label **above** the field, not as placeholder. Placeholder is a hint, not a label.
- Field height generous (44–56px).
- Hairline border `1px solid var(--rule)`. On focus: border darkens to ink + a single 1px accent underline appears, no glow halo.
- Field padding: `0.875rem 1rem`.
- Required indicator: subtle asterisk in accent color *after* the label, not red text.
- Errors: inline below the field, ink color with a small accent dot or icon — not red flooded text.
- Group related fields in a single `<fieldset>` with a small uppercase legend; hairline divider above.
- Submit: full-width on mobile, auto-width on desktop, arrow-in-circle pattern.

### Cards
- Hairline border `1px solid var(--rule)`, **no shadow** by default.
- Padding `--space-md` to `--space-lg`.
- Border-radius `8px–12px` max — no `rounded-3xl`.
- Hover (only if interactive): subtle lift via `transform: translateY(-2px)` + diffuse shadow `0 2px 16px rgba(0,0,0,0.04)`. 200ms easing.
- Eyebrow tag at top, headline next, body text, CTA at bottom.

### Navigation
- Floating navbar with margin from the top edge (NOT edge-to-edge sticky — that's the cheap-SaaS look). Container-aligned. Hairline bottom on scroll.
- Mobile menu: full-screen overlay with massive type, generous line-height, animated hamburger that morphs to X (rotate 45deg + 0deg, not just visibility toggle).

### Tables / data
- No vertical borders. Hairline horizontal dividers only.
- Numbers in tabular figures, monospace if data-heavy.
- Row hover: subtle background tint, no transformation.

### Focus styles
Default browser focus halos are banned. Swiss replacement — thin accent outline, generous offset, keyboard-only:
```css
:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
  border-radius: 2px;
}
:focus:not(:focus-visible) { outline: none; }   /* mouse focus stays clean */
```
Never `outline: none` without a `:focus-visible` replacement — that's an accessibility failure.

---

## 10. Imagery direction

- **Real over stock.** Real team photos (desaturated, warm-toned), real product screenshots, real documents, real environments. If a section has stock-shaped content, **delete it** — empty is more Swiss than fake.
- **Editorial photography** — single subject, generous negative space, restrained color. Treat photos like a magazine art director, not like a CMS image grid.
- **Illustrations:** if any, monochromatic continuous-line sketches with one offset shape filled in the brand accent. Hand-drawn feel, not vector-clean.
- **Diagrams / mockups:** wire-style simplicity. Hairline strokes. The browser/device frame, if used, is minimal — three small dots for window controls, no chrome decoration.
- **Apply a 3–5% warm grain overlay** to all photographic imagery to integrate it with the paper substrate.

### Image treatment CSS
Concrete starter for the photographic discipline above — desaturate slightly, add hairline contrast bump, layer grain through pseudo-element:
```css
img:not(.no-treatment) {
  filter: saturate(0.9) contrast(1.02);
}
figure {
  position: relative;
  isolation: isolate;
}
figure::after {                       /* warm grain over photos */
  content: '';
  position: absolute; inset: 0;
  background: url('noise.svg') repeat;
  opacity: 0.04;
  mix-blend-mode: multiply;
  pointer-events: none;
}
```

---

## 11. Mobile

- Mobile-first media queries (`min-width`).
- Asymmetric desktop layouts collapse to single column at 768px. Generous vertical gaps between stacked elements.
- Type scales appropriately via the `clamp()` system in §5.
- Eyebrow tags shrink but stay uppercase.
- Arrow-in-circle CTAs: full-width on mobile, the arrow circle stays.
- Ambient layer: keep but reduce opacity to 0.02 on mobile (battery, contrast).
- Custom cursor: hide entirely on touch via `@media (hover: none)` (handled in §8 pattern #12).
- Never `100vh` for hero — use `min-height: 100dvh`.

### Performance for long Swiss pages
Swiss publications are long. Defer off-screen sections from rendering:
```css
section {
  content-visibility: auto;
  contain-intrinsic-size: 0 800px;       /* estimate; prevents scrollbar jumps */
}
```
Saves render cost on initial paint and below-fold scroll. Pairs naturally with Lenis.

### Print stylesheet
Swiss tradition IS print. The site should print cleanly — strip chrome, restore black ink on white, expose link targets, prevent orphans:
```css
@media print {
  .ambient, .grain, .cursor, nav, footer { display: none; }
  body { background: white; color: black; max-width: 65ch; margin: 0 auto; }
  a::after { content: ' (' attr(href) ')'; font-size: 0.85em; color: #555; }
  h1, h2, h3 { page-break-after: avoid; }
  p, li     { orphans: 3; widows: 3; }
  img      { max-width: 100%; page-break-inside: avoid; }
}
```

---

## 12. Anti-pattern checklist (before declaring done)

Run through this before saying any Swiss-design work is finished:

### Foundation
- [ ] CSS variables for spacing scale (no raw pixel values)
- [ ] `lang` attribute on `<html>` uses regional subtag (`de-CH`, `fr-CH`, `it-CH`)
- [ ] `<meta name="color-scheme" content="light dark">` in `<head>`
- [ ] `font-optical-sizing: auto` set on root element

### Typography
- [ ] No Inter, Roboto, Open Sans, Arial in the font stack
- [ ] Fonts loaded with `font-display: optional` (no FOUT-flash)
- [ ] At least one type-as-architecture moment on the page
- [ ] Body line-height 1.55–1.7, max 65–75 characters per line
- [ ] Eyebrow tag pattern used consistently across major sections
- [ ] Hyphenation enabled for body, disabled for headlines

### Color
- [ ] One accent color in the entire palette (count uses in CSS — should be < 10)
- [ ] No purple, no three-color gradients, no glassmorphism
- [ ] Dark mode supported via `@media (prefers-color-scheme: dark)`
- [ ] All hairlines `1px` at low contrast; no thick borders or heavy shadows
- [ ] Subtle film grain or warm noise overlay for substrate texture

### Layout
- [ ] Hero is left-aligned (not centered)
- [ ] No `max-width` on text elements (`p`, `h1-h6`, `li`, `span`)
- [ ] Section padding from a CSS variable scale (not raw pixels)
- [ ] No equal-three-card feature row (the most generic AI layout)
- [ ] Mobile uses `100dvh` not `100vh`

### Motion & interaction
- [ ] Lenis smooth scroll installed and configured with `lerp: 0.08`
- [ ] CTAs use the arrow-in-circle pattern, custom cubic-bezier easing
- [ ] All animations respect `prefers-reduced-motion`
- [ ] Ambient parallax layer present (one, slow, low opacity)

### Accessibility & craft
- [ ] `:focus-visible` styled with Swiss accent outline; never `outline: none` without replacement
- [ ] Forms have label-above-field and hairline-only borders
- [ ] Real images only — every stock-shaped photo is deleted or replaced
- [ ] No emojis, no AI-marketing clichés in the visible copy

---

## 13. Execution protocol

When applied to a project:

**Setup (before step 1):** Install Lenis smooth scroll as the page foundation before writing any other JS. Low `lerp` = Swiss deliberateness; high `lerp` = consumer-app bounciness:
```js
import Lenis from 'lenis'
import 'lenis/dist/lenis.css'   // path varies by Lenis version; check docs
const lenis = new Lenis({ lerp: 0.08, duration: 1.2 })
function raf(time) { lenis.raf(time); requestAnimationFrame(raf) }
requestAnimationFrame(raf)
```

1. **Confirm the brand inputs:** paper substrate, ink shade, single accent (or two-shade brand pair), font choice (one neo-grotesque + optional editorial serif). If missing, ask.
2. **Lock the spacing scale and type scale** as CSS variables before touching components. These are the foundation; changing them later is painful.
3. **Build the macro-whitespace and grid first.** Get the rhythm right with empty sections before populating content. The page should look correct as wireframe.
4. **Establish the typographic hierarchy** — set H1, H2, body, eyebrow, micro-label classes globally.
5. **Add components** — arrow-in-circle CTA, hairline card, form pattern, eyebrow tag — using the global scale.
6. **Add the ambient layer + film grain** as page-level fixtures.
7. **Layer entry reveals** — CSS scroll-driven (`animation-timeline: view()`) preferred, IntersectionObserver as fallback (see §8 pattern #6). Stagger via `--i`.
8. **One wow moment per major section.** Choose from §8. Do not stack three.
9. **Run the §12 checklist.**
10. **Refine with adjacent skills** (`arrange`, `typeset`, `quieter`, `polish`) if available.

When **redesigning an existing site**:
1. Run the audit from `redesign-existing-projects` skill (if installed) to catalog AI-slop patterns.
2. Apply this skill's rules in order: substrate → typography → spacing → components → motion → wow moments.
3. Do not rewrite from scratch. Improve in-place. Each pass should be a measurable upgrade.

---

## 14. References

The skill is a synthesis of:
- Müller-Brockmann, *Grid Systems in Graphic Design* (1981)
- Emil Ruder, *Typography* (1967)
- Modern Swiss-influenced agency websites: Mobiliar (protekta.mobiliar.ch), seoagentur.de, doppio.li, favorit.studio, eseagency.ch, ewm.swiss, Stink Studios, Raffinerie AG, Studio375
- Tools & specs: Lenis (lenis.dev), CSS Scroll-Driven Animations (Chrome 115+, Safari 26+), View Transitions API (Chrome 111+, Safari 18.2+), `oklch()` (Baseline 2023), `hanging-punctuation` (Safari)
- Adjacent skills (taste-skill collection, Leonxlnx): `minimalist-ui`, `high-end-visual-design`, `industrial-brutalist-ui`, `redesign-existing-projects`, `overdrive`, `polish`, `arrange`, `typeset`

---

## 15. When to reach for an adjacent skill instead

- **Brand identity work / logo / poster:** this skill covers web; for print/poster Swiss work, use a print-design-specific tool.
- **SaaS / dashboard heavy data UI:** consider `industrial-brutalist-ui`'s Tactical Telemetry mode or a dashboard-specific skill.
- **Brutalist-aggressive aesthetic:** use `industrial-brutalist-ui` directly; this skill is the conservative-editorial cousin.
- **AI-startup or consumer-tech vibe:** use `minimalist-ui` directly; this skill assumes Swiss/editorial register.

---

## 16. Starter HTML skeleton

A minimal foundation that applies every rule in §3–§11. Copy, then strip what's not needed:

```html
<!DOCTYPE html>
<html lang="de-CH">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="color-scheme" content="light dark">
  <title>...</title>
  <style>
    :root {
      --paper:  oklch(98% 0.005 90);
      --ink:    oklch(15% 0.010 260);
      --rule:   oklch(92% 0.005 90);
      --accent: oklch(48% 0.180 25);
      --space-xs: 0.5rem;  --space-sm: 1rem;   --space-md: 1.5rem;
      --space-lg: 2.5rem;  --space-xl: 4rem;   --space-2xl: 6rem;
      --space-3xl: 8rem;   --space-4xl: 12rem;
      --text-base: clamp(1rem, 0.95rem + 0.25vw, 1.125rem);
      --text-4xl:  clamp(3rem, 2.2rem + 3.5vw, 5.5rem);
      scrollbar-color: var(--rule) var(--paper);
      scrollbar-width: thin;
    }
    html {
      font-optical-sizing: auto;
      text-rendering: optimizeLegibility;
      hanging-punctuation: first last allow-end;
    }
    body {
      background: var(--paper); color: var(--ink);
      font-family: 'Suisse Int\'l', 'Inter Tight', system-ui, sans-serif;
      font-size: var(--text-base);
      line-height: 1.6;
      font-feature-settings: "kern" 1, "liga" 1, "calt" 1;
      cursor: none;
    }
    input, textarea, [contenteditable] { cursor: text; }
    h1, h2, h3 { text-wrap: balance; line-height: 1.1; }
    p, li      { text-wrap: pretty; }
    :lang(de), :lang(de-CH) { hyphens: auto; hyphenate-limit-chars: 8 4 3; }
    :lang(fr), :lang(fr-CH) { hyphens: auto; hyphenate-limit-chars: 10 4 3; }
    h1, h2, h3, .eyebrow    { hyphens: none; }
    :focus-visible {
      outline: 2px solid var(--accent); outline-offset: 4px; border-radius: 2px;
    }
    .ambient {
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background: radial-gradient(circle at 30% 40%,
        color-mix(in oklab, var(--accent) 100%, transparent) 0%,
        transparent 60%);
      opacity: 0.04;
      animation: drift 45s ease-in-out infinite alternate;
    }
    @keyframes drift { to { transform: translate(8vw, -6vh) scale(1.1); } }
    .cursor {
      position: fixed; top: 0; left: 0; width: 8px; height: 8px;
      border-radius: 50%; background: var(--accent);
      pointer-events: none; z-index: 9999; opacity: 0;
      transition: opacity 200ms, width 200ms, height 200ms, background 200ms;
    }
    .cursor.is-active { opacity: 1; }
    .cursor.on-interactive {
      width: 32px; height: 32px;
      background: transparent; border: 1px solid var(--accent);
    }
    @media (hover: none) { body { cursor: auto; } .cursor { display: none; } }
    section { content-visibility: auto; contain-intrinsic-size: 0 800px; }
    @media (prefers-color-scheme: dark) {
      :root {
        --paper:  oklch(12% 0.010 260);
        --ink:    oklch(94% 0.005 90);
        --rule:   oklch(20% 0.010 260);
      }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
      }
    }
  </style>
</head>
<body>
  <div class="ambient"></div>
  <div class="cursor"></div>
  <!-- nav, sections, footer -->
  <script type="module">
    import Lenis from 'https://esm.sh/lenis'
    const lenis = new Lenis({ lerp: 0.08, duration: 1.2 })
    function raf(t) { lenis.raf(t); requestAnimationFrame(raf) }
    requestAnimationFrame(raf)
  </script>
</body>
</html>
```

This skeleton ships: oklch palette, dark mode, reduced-motion, hyphenation, Lenis, ambient layer, focus styles, hanging-punctuation, optical sizing, scrollbar, custom cursor, `content-visibility` perf. ~100 lines of foundation. Add components and section content on top.
