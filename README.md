# Swiss Design Skill

A skill for AI coding agents that builds websites in the Swiss design tradition. Strict grids, neo-grotesque typography, restrained color, deliberate whitespace. Produces output that looks built, not generated.

## What "Swiss design" actually means

"Swiss design" is the common shorthand for the **International Typographic Style**, a design discipline that emerged from Basel and Zurich in the late 1940s and dominated graphic design for decades. The skill translates its print principles to the web.

Two books anchor the discipline:

- **Josef Müller-Brockmann, [*Grid Systems in Graphic Design*](https://en.wikipedia.org/wiki/Grid_Systems_in_Graphic_Design) (1981).** The modular grid as information architecture.
- **Emil Ruder, [*Typography*](https://en.wikipedia.org/wiki/Emil_Ruder) (1967).** Typographic hierarchy through scale, weight, and spacing alone, without decoration.

**"Neo-grotesque"** is the category of sans-serif typefaces that defines the visual register: Helvetica, Univers, Akzidenz-Grotesk, and modern descendants like Suisse Int'l, Söhne, GT America. ([Neo-grotesque on Wikipedia](https://en.wikipedia.org/wiki/Sans-serif#Neo-grotesque))

The modern web idioms layered on top (Lenis smooth scroll, oklch color, View Transitions, ambient parallax) come from observing contemporary Swiss and Swiss-influenced studios working in this lineage.

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

Invoke when the brief calls for Swiss, editorial, minimalist-premium, or agency-clean.

```
/swiss-design
```

## License

MIT. See [LICENSE](./LICENSE).

## References

- Josef Müller-Brockmann, *Grid Systems in Graphic Design* (Niggli Verlag, 1981)
- Emil Ruder, *Typography: A Manual of Design* (Niggli Verlag, 1967)
- Richard Hollis, *Swiss Graphic Design: The Origins and Growth of an International Style 1920-1965* (Yale University Press, 2006)
