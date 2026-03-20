---
last-reconciled: 2026-03-20
status: CURRENT
Build stage: Stage 11
Drift status: CURRENT
vision-alignment: 100%
---

# SPEC

## Identity

Claude Code Artifacts provides two Claude Code slash commands (`/visualize` and `/blueprint`) that generate interactive HTML pages from natural language descriptions. Each command is a detailed prompt file (678 and 639 lines respectively) that defines a complete design system, animation system, structural patterns, and embedded data model. The prompts instruct Claude Code to scan the codebase, understand the architecture, and render it as a self-contained HTML file. This repo is archived; both skills have migrated to Squire.

## Current Capabilities

### 1. Visualize Skill (/visualize)

- **Interactive HTML generation:** Generates standalone HTML pages explaining architecture, workflows, or concepts visually from natural language descriptions.
- **Tabbed views:** Multi-faceted topics organized into tabs (overview, details, cheatsheet) for progressive disclosure.
- **Animated SVG flow diagrams:** Directional flow lines with traveling dots for architecture and workflow visualization.
- **Standardized node components:** 7 SVG node shapes for consistent architecture diagram vocabulary.
- **Interactive cards:** Expand/collapse cards for progressive disclosure of detail.
- **Assessment framework:** Persistent checkboxes, severity badges, and copy-paste fix prompts that make artifacts actionable.
- **Embedded JSON data model:** Every artifact carries structured JSON for programmatic updates and re-reading.

### 2. Blueprint Skill (/blueprint)

- **Structured interview:** 6-round interview (scope, architecture, phases, parallelism, risks, confirmation) before generating output.
- **Phase cards:** Sequential tasks and parallel batch columns organized by implementation phase.
- **SVG dependency graph:** Auto-layout dependency graph rendered from embedded JSON data.
- **Hover-to-trace:** Highlights upstream (amber) and downstream (teal) dependencies on hover.
- **Progress tracking:** localStorage-persistent checkboxes with real-time progress bars.
- **Batch prompts:** One-paste agent distribution prompts for parallelizable work.
- **Update flag:** `--update` re-reads embedded JSON and merges new progress without regenerating from scratch.

### 3. Design System

- **Factory-Inspired visual language:** Near-black (#020202) background, near-white (#eeeeee) text, orange (#ef6f2e) primary, amber (#f59e0b) secondary, teal (#4ecdc4) tertiary.
- **Typography:** Light-weight headings (font-weight 400) with tight letter-spacing. Body text in monospace.
- **Visual philosophy:** No shadows, gradients, or glow effects. Typography and whitespace carry the entire visual hierarchy.

### 4. Archive Status

- **Migrated to Squire:** Both skills now live in github.com/eddiebelaval/squire as the unified Claude Code toolkit.
- **Redirect in place:** README points users to Squire for the latest versions.
- **Published on GitHub:** Repo remains available for existing users under MIT license.

## Architecture Contract

### Stack

| Layer | Technology | Notes |
|-------|-----------|-------|
| Product | Markdown prompt files | 678 lines (visualize), 639 lines (blueprint) |
| Output | Standalone HTML | Zero dependencies, self-contained |
| Design system | CSS-in-prompt | Color tokens, typography, animation rules baked into prompts |
| Data layer | Embedded JSON | Carried inside generated HTML for re-reading |
| License | MIT | Open source |

### System Role

Claude Code Artifacts is a prompt-only skill set for Claude Code. It has no runtime, no server, and no dependencies. It generates standalone HTML files that live wherever the user saves them.

### Primary Actors

- `Developer` -- invokes `/visualize` or `/blueprint` within a Claude Code session
- `Claude Code` -- reads the prompt files, scans the codebase, and generates HTML output
- `Squire` -- the successor repo that now hosts and maintains both skills

### Data Flow

```
Developer invokes /visualize or /blueprint
  -> Claude Code reads prompt file (commands/)
  -> Claude Code scans codebase context
  -> Claude Code generates standalone HTML
  -> HTML saved to local filesystem (~/Development/artifacts/)
  -> HTML contains embedded JSON for future --update cycles
```

### Core Entities

| Entity | Purpose | Key Fields |
|--------|---------|------------|
| Prompt file | The product itself: complete specification for HTML generation | Design system, animation rules, structural patterns, JSON schema |
| Generated artifact | Standalone HTML page | Tabs, SVG diagrams, interactive cards, embedded JSON |
| Embedded JSON | Structured data model inside each artifact | Component tree, dependencies, progress state |

### Integrations

| Service | Purpose | Status |
|---------|---------|--------|
| Claude Code | Execution surface for prompt files | Active |
| Squire | Successor repo hosting latest versions | Active |
| GitHub | Public distribution (MIT) | Active |

## Current Boundaries

- Does NOT have a runtime, server, or build pipeline
- Does NOT install dependencies or require `npm install`
- Does NOT generate framework components (React, Vue, etc.): output is always standalone HTML
- Does NOT support non-macOS file saving paths natively (artifacts directory convention)
- Does NOT receive active development: all new work happens in Squire
- Does NOT provide a CLI or API: invocation is through Claude Code slash commands only

## Verification Surface

### Skills
- [ ] `/visualize` prompt file exists at `commands/visualize.md` and is readable by Claude Code
- [ ] `/blueprint` prompt file exists at `commands/blueprint.md` and is readable by Claude Code
- [ ] Generated HTML artifacts are self-contained (no external CSS/JS dependencies)
- [ ] Embedded JSON data model is present in generated artifacts

### Design System
- [ ] Color tokens match Factory-Inspired palette (#020202, #eeeeee, #ef6f2e, #f59e0b, #4ecdc4)
- [ ] No shadows, gradients, or glow effects in generated output

### Archive
- [ ] README redirects users to Squire
- [ ] Repo is publicly accessible on GitHub under MIT license

## Drift Log

| Date | Section | What Changed | Why | VISION Impact |
|------|---------|-------------|-----|---------------|
| 2026-02-01 | Initial | First spec written alongside v0.1 | Project creation | None |
| 2026-02-15 | Capabilities | Added /blueprint skill | Planning counterpart to /visualize | Pillar 2 realized |
| 2026-02-28 | Status | v1.0 published as MIT open source | Ready for public use | None |
| 2026-03-18 | Archive | Both skills migrated to Squire, repo archived | Squire unified toolkit formed | Pillar 3 realized, all pillars complete |
| 2026-03-20 | Format | Upgraded to v2 TRIAD format (YAML frontmatter, Architecture Contract, Verification Surface) | Consistency with golden sample | None |
