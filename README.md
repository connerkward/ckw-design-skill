# ckw-design

**ckw-design** is Conner K. Ward's frontend design skill for Claude Code — direction, design system, and visual philosophy distilled into a loadable skill: how to set tone/domain/color-world, build tokens and typography, and hold a high review bar.

> **What this is:** A personal design skill — direction and taste, packaged. (For the deterministic measurement/judgment layer, see deterministic-design.)

## Install (Claude Code plugin)

```
/plugin marketplace add connerkward/ckw-design-skill
/plugin install ckw-design@ckw-design
```

Or install the whole set: `/plugin marketplace add connerkward/connerkward-skills`. Or drop this repo's `SKILL.md` into your agent's skills directory.

## License

MIT © Conner K Ward

---

# Claude Design Skills

**Claude Code skills for frontend design** — five composable agent skills that push Claude toward distinctive, production-grade UI design and away from generic AI aesthetics (Inter, purple gradients, three equal cards, centered single-column mush).

They cover design direction, design systems (tokens, typography, color), spatial composition and layout, loading/FOUT discipline, motion timing, and high-concept art direction — for any web UI work: components, pages, dashboards, landing pages, React/Vue/plain HTML-CSS.

![Before / after: a generic AI landing page vs the same page with these skills applied](docs/before-after.png)

## What's inside

| Skill | File | When it loads |
|---|---|---|
| **design** (entry) | [`design/SKILL.md`](design/SKILL.md) | Any time Claude builds or touches the look of a web UI — styling, spacing, layout, typography, color, polish, "make this look better" — even without the word "design". Routes to the four sub-skills. |
| **design-thinking** | [`design/design-thinking/SKILL.md`](design/design-thinking/SKILL.md) | Every design task, before coding. Defines purpose, tone, domain vocabulary, color world, a review bar, and a cross-domain lens (cinema, architecture, marketing, UX, automotive, industrial design). |
| **design-system** | [`design/design-system/SKILL.md`](design/design-system/SKILL.md) | When implementing: token architecture, typography hierarchy, resource loading order, FOUT prevention (no font pop-in, ever), graceful loading states, layout-stable chrome, motion timing, color semantics. |
| **design-spatial** | [`design/design-spatial/SKILL.md`](design/design-spatial/SKILL.md) | When composing layout, or when generated UI looks off — collisions, weak hierarchy, "looks like every startup site". Render-then-critique loop with a separate judge; deliberate deviation from the statistical mean. |
| **design-philosophy** | [`design/design-philosophy/SKILL.md`](design/design-philosophy/SKILL.md) | High-concept work, campaigns, visual manifestos, unmistakable art-like aesthetics. Includes a [reference](design/design-philosophy/reference.md) of condensed philosophy examples. |

## Install

Claude Code discovers skills in `~/.claude/skills/` (user-wide) or `<project>/.claude/skills/` (per-project). Copy the `design/` directory there:

```bash
# user-wide (all projects)
git clone https://github.com/connerkward/claude-design-skills.git
mkdir -p ~/.claude/skills
cp -R claude-design-skills/design ~/.claude/skills/design
```

```bash
# or per-project
mkdir -p .claude/skills
cp -R claude-design-skills/design .claude/skills/design
```

That's it — no build step, no dependencies. The skills are plain Markdown prompt content. Restart Claude Code (or start a new session) and they're available.

## How skills trigger

Each `SKILL.md` has YAML frontmatter with a `name` and a `description`. Claude Code injects all skill descriptions into the model's context; when a task matches a description, Claude loads that skill's full body on demand. The descriptions here are written to be "pushy" — they fire on styling, spacing, fonts, color, responsiveness, and "make it look nicer", not just the literal word "design".

The entry skill (`design`) is the router: it loads first and tells Claude which sub-skills to pull in for the task at hand (direction → `design-thinking`, implementation → `design-system`, layout → `design-spatial`, art direction → `design-philosophy`). Sub-skill bodies are only read when relevant, keeping context cost low.

## Philosophy

A language model's first design idea is the average of its training data — and there is more than one average: the generic-AI mean (Inter, purple-on-white, three equal cards) and the flashier designer-trend mean (oversized condensed caps, dark mode + grain, monospace "vibes" microtext). Neither is taste. These skills insist on two disciplines instead of prescribing a style: **look at the rendered output with fresh eyes** (a model can't see the collisions in its own token stream — screenshot it and have a separate judge critique the image), and **deviate from the first instinct toward the product's specific world** — its domain vocabulary, its color world, one signature element that could only exist for this product. Process over prescription; intentionality over intensity.

## License

MIT — see [LICENSE](LICENSE).

---

🧭 **[ckw-skills](https://github.com/connerkward/ckw-skills)** — part of Conner K. Ward's collection of Claude Code skills & MCP servers.
