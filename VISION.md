---
last-evolved: 2026-03-18
confidence: HIGH
distance: 0%
pillars: "3 (3 realized, 0 partial, 0 unrealized)"
---

# VISION

## Soul

Give developers a way to see their systems -- architecture, workflows, and build plans rendered as interactive HTML artifacts with a consistent design language, generated entirely through AI prompt engineering.

## Why This Exists

Most developer tooling focuses on writing code, not understanding it. Architecture docs go stale. Diagrams live in external tools disconnected from the codebase. Claude Code Artifacts exists because the best time to visualize a system is while you are already inside it, talking to an AI that can read the code. The prompts ARE the product: no dependencies, no build step, no server. A well-specified prompt is a reusable tool.

## Pillars

### 1. **Visualize Skill** -- REALIZED

The `/visualize` command generates interactive HTML pages that explain architecture, workflows, codebases, or concepts visually. Includes tabbed views, animated SVG flow diagrams with traveling dots, standardized node components (7 shapes), interactive expanding cards, assessment tabs with persistent checkboxes, and embedded JSON data models for programmatic updates. 678-line prompt file defining a complete design system.

### 2. **Blueprint Skill** -- REALIZED

The `/blueprint` command generates interactive build plans through a 6-round structured interview (scope, architecture, phases, parallelism, risks, confirmation). Outputs include phase cards with sequential tasks and parallel batch columns, auto-layout SVG dependency graphs, hover-to-trace dependency highlighting (amber upstream, teal downstream), localStorage-persistent progress tracking, batch prompts for agent distribution, and a `--update` flag for re-reading embedded JSON. 639-line prompt file.

### 3. **Migration to Squire** -- REALIZED

Both skills have been migrated to the Squire repository, which serves as the unified toolkit for all Claude Code productivity tools. This repo now functions as an archive and redirect. The README points users to Squire for the latest versions.

## User Truth

**Who:** Developers using Claude Code who need to explain, plan, or audit complex systems but lack a fast way to produce visual artifacts from within their AI workflow.

**Before:** "I know my system is complex but I can't show anyone what it looks like. Drawing diagrams takes forever and they go stale immediately. Build plans live in my head or in a doc nobody reads."

**After:** "I type `/visualize` and get an interactive HTML page I can share. I type `/blueprint` and get a build plan with dependency graphs and progress tracking. The artifact IS the documentation."

## Phased Vision

### Phase 1 -- Prompt-as-Product (COMPLETE)

Prove that a single prompt file can reliably generate consistent, high-quality interactive HTML artifacts. Codify a design system, animation rules, and structural patterns directly into the prompt specification.

### Phase 2 -- Planning Counterpart (COMPLETE)

Extend the pattern from visualization to planning. Build `/blueprint` as the forward-looking complement to `/visualize`, adding interview structure, dependency graphs, and progress tracking.

### Phase 3 -- Consolidation into Squire (COMPLETE)

Migrate both skills into the unified Claude Code toolkit (Squire). Archive this repo as the origin point and redirect users to the successor project.

## Edges

- Archived: all active development continues in Squire
- macOS-centric for local file saving
- Assumes Claude Code as the agent surface
- HTML artifacts are standalone files, not components in a framework
- Does NOT provide a runtime library or build tool
- Does NOT require external dependencies, a server, or a build pipeline

## Anti-Vision

- Never become a runtime library or dependency. The prompts ARE the product.
- Never require a build step, server, or external infrastructure. If the skills need `npm install`, the design philosophy is broken.
- Never couple to a specific framework. The output is standalone HTML, not React components.

## Design Principles

- Prompts are the product. Complexity lives in specification, not in code.
- Standalone output. Every generated artifact works as a single HTML file with zero dependencies.
- Factory-Inspired visual language. Near-black, near-white, orange accents. Typography and whitespace carry hierarchy, not shadows or gradients.
- Progressive disclosure. Interactive cards, tabbed views, and expanding sections let the viewer control depth.
- Embedded data models. Every artifact carries its own JSON so it can be re-read, updated, and regenerated without starting from scratch.

## Evolution Log

| Date | What Shifted | Signal | Section |
|------|-------------|--------|---------|
| 2026-02-01 | Initial vision: prompt-based HTML visualization | First consistent outputs from codified design system | Soul, Pillars |
| 2026-02-15 | Added /blueprint as planning counterpart | /visualize proved the pattern; planning was the natural complement | Pillars |
| 2026-02-28 | Published as MIT open source | v1.0 release on GitHub | Pillars |
| 2026-03-18 | Archived: migrated to Squire | Squire formed as unified toolkit; skills are natural candidates | Pillars, Edges |
