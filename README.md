# Claude Code Artifacts

> **This repo has moved.** All tools — including `/visualize`, `/blueprint`, `BUILDING-SETUP.md`, and more — now live in **[id8-toolkit](https://github.com/eddiebelaval/id8-toolkit)**. Head there for the latest versions, new tools, and the install script.

---

*The original `/visualize` and `/blueprint` files below still work, but id8-toolkit is where everything gets updated going forward.*

## Installation

```bash
cp commands/visualize.md ~/.claude/commands/
cp commands/blueprint.md ~/.claude/commands/
```

Then in any Claude Code session:

```
/visualize Homer architecture
/visualize how our auth flow works
/blueprint new dashboard feature
/blueprint --update my-project
```

## The Two Skills

### /visualize — Explain What Exists

Generates interactive HTML pages that explain architecture, workflows, codebases, or concepts visually. Each artifact includes:

- **Tabbed views** for multi-faceted topics (overview, details, cheatsheet)
- **Animated SVG flow diagrams** with directional flow lines and traveling dots
- **Standardized SVG node components** — 7 reusable shapes for architecture diagrams
- **Interactive cards** that expand/collapse for progressive disclosure
- **Assessment tab** with persistent checkboxes, severity badges, and copy-paste prompts
- **Embedded JSON data model** for programmatic updates

### /blueprint — Plan What to Build

Generates interactive build plans with a 6-round structured interview before producing HTML. Each blueprint includes:

- **Conversational intake** — 6 rounds of structured questions (scope, architecture, phases, parallelism, risks, confirmation)
- **Phase cards** with sequential tasks and parallel batch columns
- **Parallel Map** — auto-layout SVG dependency graph rendered from JSON data
- **Hover-to-trace** — hover any task to highlight its upstream (amber) and downstream (teal) dependencies
- **Progress tracking** — localStorage-persistent checkboxes with real-time progress bars
- **Batch prompts** — one-paste prompts for entire parallel batches, ready for agent distribution
- **`--update` flag** — re-read the embedded JSON, merge new progress, regenerate the HTML

## How It Works

Each skill file is a detailed prompt (678 lines for visualize, 639 for blueprint) that defines:

1. **A complete design system** — color tokens, typography, components, layout rules
2. **An animation system** — staggered reveals, flowing SVG dashes, traveling dots, stat counters
3. **Structural patterns** — tabs, cards, diagrams, checklists
4. **An assessment framework** — actionable fixes and next steps with copy-paste prompts
5. **An embedded data model** — JSON block in every artifact for programmatic re-reading and updates

The prompts are the product. Claude Code reads them, understands the design language, and generates consistent artifacts every time.

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

### /visualize examples
- **`hackathon-kickoff-transcript.html`** — A formatted conversation transcript with speaker cards, tabbed views, and topic sections
- **`shelf-architecture.html`** — A full system architecture visualization with animated SVG flow diagrams, file tree, data flow steps, assessment checklists with localStorage persistence, and embedded JSON data model

### /blueprint examples
- **`parallax-blueprint.html`** — A real build plan for a hackathon project, showing phased tasks, parallel batches, dependency mapping, and progress tracking

## Customization

The design system lives inside each `.md` file. To adapt it:

- **Change colors:** Edit the CSS custom properties in the "Color Tokens" section
- **Change fonts:** Swap the font stack in the "Typography" section
- **Change structure:** Modify the "Component Patterns" section
- **Remove assessment tab:** Delete the "Senior Dev Assessment Tab" section (though we recommend keeping it — it makes every artifact actionable)

Both skills share the same design system. Change it in `visualize.md` and mirror the changes in `blueprint.md`, or fork each to have its own look.

## How This Was Built

These skills were developed iteratively through conversations with Claude Code. There is no traditional source code — the prompts were refined across dozens of artifacts until the design system was consistent and the outputs were reliably high-quality.

The process:
1. Started with a vague "make me an HTML visualization"
2. Noticed inconsistencies across outputs (different colors, fonts, spacing)
3. Codified a design system into the prompt
4. Added animation rules after seeing what worked
5. Added the assessment framework to make artifacts actionable, not just educational
6. Built `/blueprint` as the planning counterpart — same system, opposite direction
7. Added embedded JSON data models to enable programmatic updates and the `--update` flow
8. Kept iterating

The lesson: a well-specified prompt is a reusable tool.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- That's it

## License

MIT
