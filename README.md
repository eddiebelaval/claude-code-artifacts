# /visualize — A Claude Code Skill for Interactive HTML Artifacts

A single-file [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that generates self-contained, interactive HTML visualizations from natural language descriptions.

Type `/visualize [topic]` and get a zero-dependency HTML page with dark theme, tabbed views, animated flow diagrams, and actionable assessment checklists — all from one prompt.

## What It Does

Instead of explaining architecture, workflows, or systems as walls of text, `/visualize` produces interactive HTML pages you can open in a browser, share with teammates, or commit to a repo.

Each artifact includes:

- **Tabbed views** for multi-faceted topics (overview, details, cheatsheet)
- **Animated SVG flow diagrams** with directional flow lines and traveling dots
- **Interactive cards** that expand/collapse for progressive disclosure
- **Assessment tab** with persistent checkboxes (localStorage), severity badges, and copy-paste prompts
- **Embedded JSON data model** for programmatic updates

Everything is a single `.html` file. No CDN links. No build step. No dependencies.

## Installation

Copy one file:

```bash
cp commands/visualize.md ~/.claude/commands/
```

Then in any Claude Code session:

```
/visualize Homer architecture
/visualize how our auth flow works
/visualize the deployment pipeline
/visualize difference between REST and GraphQL
```

## How It Works

The skill file (`visualize.md`) is a 678-line prompt that defines:

1. **A complete design system** — color tokens, typography scale, component patterns, layout rules
2. **An animation system** — staggered reveals, flowing SVG dashes, traveling dots, stat counters
3. **Structural patterns** — tabs, cards, flow diagrams, assessment checklists
4. **Standardized SVG components** — 7 reusable node shapes for architecture diagrams
5. **Assessment framework** — every artifact ends with actionable fixes, next steps, and copy-paste prompts
6. **Embedded data model** — JSON block in every artifact for programmatic re-reading and updates

The prompt is the product. Claude Code reads it, understands the design language, and generates consistent artifacts every time.

## Design System

The visual language is called "Factory-Inspired" — adapted from factory.ai.

| Token | Value | Usage |
|-------|-------|-------|
| Background | `#020202` | Near-black (not pure black) |
| Text | `#eeeeee` | Near-white (not pure white) |
| Accent | `#ef6f2e` | Orange — primary highlights |
| Secondary | `#f59e0b` | Amber — secondary emphasis |
| Success | `#4ecdc4` | Teal — rare, for success states |
| Grays | Warm/brownish | Never cool or blue-toned |

**Typography:** Light-weight headings (font-weight 400) with tight letter-spacing. Body text in monospace. No bold headings — size and spacing carry the hierarchy.

**Rules:** No shadows. No gradients. No glow effects. Generous whitespace. The typography and spacing ARE the design.

## Examples

Open the example files in `examples/` in your browser:

- **`hackathon-kickoff-transcript.html`** — A formatted conversation transcript with speaker cards, tabbed views, and topic sections
- **`shelf-architecture.html`** — A full system architecture visualization with animated SVG flow diagrams, file tree, data flow steps, assessment checklists with localStorage persistence, and embedded JSON data model

## Customization

The design system lives entirely inside `visualize.md`. To adapt it:

- **Change colors:** Edit the CSS custom properties in the "Color Tokens" section
- **Change fonts:** Swap the font stack in the "Typography" section
- **Change structure:** Modify the "Component Patterns" section
- **Remove assessment tab:** Delete the "Senior Dev Assessment Tab" section (though we recommend keeping it — it makes every artifact actionable)

## How This Was Built

This skill was developed iteratively through conversations with Claude Code. There is no traditional source code — the prompt was refined across dozens of artifacts until the design system was consistent and the outputs were reliably high-quality.

The process:
1. Started with a vague "make me an HTML visualization"
2. Noticed inconsistencies across outputs (different colors, fonts, spacing)
3. Codified a design system into the prompt
4. Added animation rules after seeing what worked
5. Added the assessment framework to make artifacts actionable, not just educational
6. Added embedded JSON data models to enable programmatic updates
7. Kept iterating

The lesson: a well-specified prompt is a reusable tool.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- That's it

## License

MIT
