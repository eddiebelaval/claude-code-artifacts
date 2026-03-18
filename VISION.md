# VISION.md — Claude Code Artifacts

> Interactive HTML visualization and build planning for Claude Code.

---

## Soul

Give developers a way to see their systems -- architecture, workflows, and build plans rendered as interactive HTML artifacts with a consistent design language, generated entirely through AI prompt engineering.

## Pillars

1. **Visualize Skill** -- REALIZED
   The `/visualize` command generates interactive HTML pages that explain architecture, workflows, codebases, or concepts visually. Includes tabbed views, animated SVG flow diagrams with traveling dots, standardized node components (7 shapes), interactive expanding cards, assessment tabs with persistent checkboxes, and embedded JSON data models for programmatic updates. 678-line prompt file defining a complete design system.

2. **Blueprint Skill** -- REALIZED
   The `/blueprint` command generates interactive build plans through a 6-round structured interview (scope, architecture, phases, parallelism, risks, confirmation). Outputs include phase cards with sequential tasks and parallel batch columns, auto-layout SVG dependency graphs, hover-to-trace dependency highlighting (amber upstream, teal downstream), localStorage-persistent progress tracking, batch prompts for agent distribution, and a `--update` flag for re-reading embedded JSON. 639-line prompt file.

3. **Migration to Squire** -- REALIZED
   Both skills have been migrated to the Squire repository, which serves as the unified toolkit for all Claude Code productivity tools. This repo now functions as an archive and redirect. The README points users to Squire for the latest versions.

---

## Anti-Vision

This was never meant to be a runtime library or a build tool. The prompts ARE the product. If the skills ever require external dependencies, a server, or a build pipeline, the design philosophy has been violated.

## Edges

- Archived -- all active development continues in Squire
- macOS-centric for local file saving
- Assumes Claude Code as the agent surface
- HTML artifacts are standalone files, not components in a framework
