---
name: deterministic-design
description: Deterministic, measurable design verification — render the UI and PROVE it's balanced and usable instead of trusting the model's eye. Layout audit (centroid / optical-center / pixel-oracle balance via deterministic math, annotated screenshot) + a vision-judged Nielsen usability audit by a SEPARATE fresh-eyes judge. Use to catch AI-generated UI that "looks off", is misaligned / centered-mush, or fails usability — the measurement+judgment layer that token-and-taste design skills (including the default) don't have.
author: Conner K Ward
---

# deterministic-design

Thesis: **determinism beats AI randomness.** A model can't trust its own eye on layout — so
don't. Render the UI and *measure* it.

Two sub-skills (load as needed):
- **[design-spatial](design-spatial/SKILL.md)** — deterministic layout audit: explicit grid
  + 8-pt spacing, and `layout-audit.js` computes centroid / optical-center / pixel-oracle
  balance and draws an annotated screenshot. **Numbers, not vibes.** Plus a render-then-
  critique vision loop.
- **[design-ux](design-ux/SKILL.md)** — usability audit: scores the rendered UI against
  Nielsen's 10 + interaction heuristics via a SEPARATE fresh-eyes judge → prioritized fix list.

This **improves** existing design skills (including the default Anthropic one) by adding the
layer they lack — it doesn't just advise on taste, it renders, measures, and judges the
output. Composable with any design skill.

In central this lives as a subdir of ckw-design; it **publishes separately** as
`deterministic-design-skill` (its own distribution) via publish-skill. One of the two
flagship narratives — the *determinism* one; its sibling is human-in-the-loop (lookdev).
