# SPEC.md — Claude Code Artifacts

> /visualize and /blueprint skills for generating interactive HTML architecture diagrams and build plans in Claude Code.

Build stage: Stage 11
Drift status: CURRENT
Last updated: 2026-03-18

---

## Overview

Claude Code Artifacts provides two Claude Code slash commands -- `/visualize` and `/blueprint` -- that generate interactive HTML pages from natural language descriptions. Each command is a detailed prompt file (678 and 639 lines respectively) that defines a complete design system, animation system, structural patterns, and embedded data model. The prompts instruct Claude Code to scan the codebase, understand the architecture, and render it as a self-contained HTML file. This repo is now archived; both skills have migrated to Squire (github.com/eddiebelaval/squire) where active development continues.

## Skills

### /visualize
- Generates interactive HTML pages explaining architecture, workflows, or concepts
- Tabbed views for multi-faceted topics (overview, details, cheatsheet)
- Animated SVG flow diagrams with directional flow lines and traveling dots
- 7 standardized SVG node components for architecture diagrams
- Interactive cards with expand/collapse for progressive disclosure
- Assessment tab with persistent checkboxes, severity badges, and copy-paste prompts
- Embedded JSON data model for programmatic updates

### /blueprint
- 6-round structured interview before generating output (scope, architecture, phases, parallelism, risks, confirmation)
- Phase cards with sequential tasks and parallel batch columns
- Auto-layout SVG dependency graph rendered from JSON data
- Hover-to-trace: highlights upstream (amber) and downstream (teal) dependencies
- localStorage-persistent checkboxes with real-time progress bars
- Batch prompts for one-paste agent distribution
- `--update` flag to re-read embedded JSON and merge new progress

## Design System

Factory-Inspired visual language: near-black (#020202), near-white (#eeeeee), orange (#ef6f2e), amber (#f59e0b), teal (#4ecdc4). Light-weight headings (font-weight 400) with tight letter-spacing. Body text in monospace. No shadows, gradients, or glow effects.

## Status

Archived. All tools migrated to Squire. This repo remains published on GitHub for existing users and redirects to the successor project.
