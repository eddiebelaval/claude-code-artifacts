# BUILDING.md — Claude Code Artifacts

> The origin story of /visualize and /blueprint -- prompt engineering as product development.

Last updated: 2026-03-18

---

## How It Started

The project began with a vague request: "make me an HTML visualization." The first outputs were inconsistent -- different colors, fonts, and spacing every time. The fix was to codify a design system directly into the prompt. Once the visual language was stable, animation rules were added based on what looked good across dozens of generated artifacts. The assessment framework came next, making every artifact actionable with copy-paste fix prompts instead of just educational.

## Key Decisions

**Prompts as product.** The entire project is two markdown files. No JavaScript library, no React components, no build step. The prompts contain enough specification that Claude Code generates consistent, high-quality HTML artifacts every time. This proved that a well-specified prompt IS a reusable tool.

**Embedded JSON data model.** Every generated artifact contains a JSON block that describes its structure programmatically. This enabled the `--update` flag on /blueprint -- the agent re-reads the embedded JSON, merges new progress, and regenerates the HTML without starting from scratch.

**Factory-Inspired design system.** Near-black backgrounds, near-white text, orange accents. No shadows, no gradients, no glow. Typography and whitespace carry the entire visual hierarchy. This system was refined over dozens of iterations until it produced consistently clean output.

## Build Timeline

1. **v0.1** -- First `/visualize` prompt with basic HTML generation
2. **v0.2** -- Codified design system (color tokens, typography, component patterns)
3. **v0.3** -- Added animation system (staggered reveals, flowing SVG dashes, traveling dots)
4. **v0.4** -- Added assessment framework with actionable fix prompts
5. **v0.5** -- Built `/blueprint` as the planning counterpart (same design system, opposite direction)
6. **v0.6** -- Added embedded JSON data models for programmatic re-reading and updates
7. **v1.0** -- Published as MIT-licensed open source on GitHub (Feb 2026)
8. **Archived** -- Both skills migrated to Squire (Mar 2026). Repo now redirects.

## Migration to Squire

When Squire formed as the unified Claude Code toolkit (collecting behavioral rules, slash commands, skills, agents, and pipelines into one repo), `/visualize` and `/blueprint` were natural candidates for inclusion. They migrated in March 2026. The original repo README now points users to Squire, and no further development happens here.
