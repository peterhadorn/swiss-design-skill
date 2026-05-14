# Swiss Design Skill

A skill for AI coding agents that teaches them to build websites in the **Swiss / International Typographic Style** — Müller-Brockmann grids, neo-grotesque type, ink-on-paper restraint, modern agency-grade idioms.

Produces output that looks deliberately built — not "another AI landing page."

## What's inside

- Strict bans on AI-template fingerprints (Inter, purple gradients, glassmorphism, shadcn defaults, Tailwind UI hero, bento-as-default)
- 12-column Müller-Brockmann grid with modular spacing scale
- Fluid `clamp()` type scale, variable font weights, OpenType features
- `oklch()` color, dark mode, hairline rules, single-accent discipline
- 13 wow patterns (type-as-architecture, arrow-in-circle CTA, ambient parallax, Lenis smooth scroll, CSS scroll-driven reveals, line-mask text reveal, custom cursor, View Transitions, more)
- Regional hyphenation (`de-CH`, `fr-CH`, `it-CH`)
- Accessibility (`:focus-visible`, `prefers-reduced-motion`, `prefers-color-scheme`)
- Print stylesheet, `content-visibility` performance
- Drop-in starter HTML skeleton (~100 lines)
- Anti-pattern checklist before declaring done

## Install

**Claude Code:**
```bash
git clone https://github.com/peterhadorn/swiss-design-skill ~/.claude/skills/swiss-design
```

**Codex:**
```bash
git clone https://github.com/peterhadorn/swiss-design-skill ~/.codex/skills/swiss-design
```

Symlink instead if you want one source of truth with live updates.

## Use

Invoke when the brief calls for Swiss, editorial, minimalist-premium, agency-clean, or references agencies like Mobiliar, Doppio, favorit.studio, eseagency.ch, Stink Studios.

```
/swiss-design
```

## License

MIT — see [LICENSE](./LICENSE).

## Credits

Built on Müller-Brockmann's *Grid Systems* (1981) and Ruder's *Typography* (1967), translated into 2026 web idioms. Synthesized from award-winning Swiss agency websites.
