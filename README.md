# Workstations — a memory & token method for Claude Cowork

A structured way to run Claude Cowork projects that stays lean over time instead of accumulating instruction bloat. Adapted from Jeff Su's Cowork memory/token method (see `/resources/jeff-su-cowork-guide.md` for the original).

**Status: in progress.** The structure is live and in daily use; the results below are being collected as real sessions happen, not backfilled. See [Results](#results) and `/resources/benefits-log.md`.

## The problem this solves

A single growing `CLAUDE.md` (or memory file) tends toward two failure modes: it either stays short and vague, so Claude re-learns your preferences every session, or it grows without bound, so every session pays the token cost of re-reading rules that rarely change. This method separates the two kinds of content so each can be optimized on its own terms.

## Core idea

Two layers, split by how often content changes:

- **Rules** (stable, prescriptive — "always/never," "before X do Y") live in `CLAUDE.md`, capped at 300 lines. This file auto-loads every session.
- **Facts** (things that could change — current status, active projects, tools in use) live in Claude's built-in persistent memory, not in a file in this repo.

A simple placement test decides where any new note goes: is it a standing rule, or a fact that could go stale? Rule → `CLAUDE.md`. Fact → memory.

## Structure

```
CLAUDE.md                  — root rules, routing map, under 300 lines
/workstations/             — one folder per "place you work" (human judgment required)
/skills/                   — plain-markdown checklists for repeatable, no-judgment tasks
/resources/                — reference docs, loaded on demand only
```

A **workstation** is not the same as a Cowork **Skill** (an installed, auto-triggered plugin) or a **skill file** in `/skills` (a checklist Claude runs start-to-finish on request). Keeping these three concepts distinct is one of the method's core rules — conflating them is the most common way a setup like this drifts.

## Quickstart (adapting this for your own project)

1. Copy `CLAUDE.md` into your project root and strip the example content, keeping the section structure (Memory System, Preferences, Rules, Routing Map, Workstations, Skills, References).
2. Read `/resources/creating-new-workstations.md` before adding your first workstation folder.
3. Set your own placement test in Section 1 if "rule vs. fact" doesn't fully capture your split.
4. Start a benefits log of your own (see below) if you want evidence of what changed, not just a feeling that it helped.

**Faster path:** if you're using Claude Cowork, install the companion skill below and just ask it to bootstrap or migrate a project — it automates steps 1–3, including turning an already-messy `CLAUDE.md` into this structure without losing content.

## Companion Skill

`/claude-skills/workstation-bootstrap` is a tested, installable Cowork Skill that automates everything above. (The folder is named for the platform, not the repo — future skills built for other platforms will get their own sibling folder rather than mixing in here.) It bootstraps a brand-new project, migrates an existing bloated one onto this structure, and ships two built-in guardrails: it never lets facts go stranded if memory-seeding is interrupted, and it proactively suggests a fresh chat when a session's quality starts to drift instead of pushing through a degraded context window. Benchmarked internally at 100% (33/33 assertions) against a stricter test suite than the method's first version — see the repo's benefits log for the before/after methodology.

The folder holds the skill's source (`SKILL.md` + `assets/`). To produce an installable `.skill` file from it, package it with Anthropic's `skill-creator` skill (`python -m scripts.package_skill /path/to/workstation-bootstrap`).

## Results

Token usage isn't visible as an automatic dashboard for individual Claude accounts — that requires a Team or Enterprise plan. So results here come from manually logging sessions via the `explain-usage` skill rather than a live graph. `/resources/benefits-log.md` has the raw entries and the methodology; this section will summarize the trend once there's enough data to summarize honestly.

## License

[MIT](LICENSE) — use, modify, and redistribute freely, including commercially; just keep the copyright notice attached.
