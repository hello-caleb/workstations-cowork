# CLAUDE.md

Root instruction set for the Workstations workspace (Jeff Su's Cowork method, adapted). Hard ceiling: 300 lines; target 200–250. Task-specific content lives in `/workstations`, `/skills`, or `/resources` — not here.

**Load note (verified Aug 2026):** Cowork auto-loads this file every session. The project's Instructions field stays empty — do not paste content there, or it will load twice.

---

## 1. Memory System

Claude uses its built-in persistent memory (individual typed files + auto-loaded index) instead of a separate MEMORY.md/archive.md. Jeff Su's cascading-memory pattern maps onto it: one memory file per project/workstation, root index holds one line each.

**Placement test (apply to every entry):**
- Prescriptive ("always/never", "before X do Y") → belongs in this file or a workstation claude.md
- A fact that could change (status, tools in use, current projects) → belongs in built-in memory

**Entry hygiene:** 1–2 sentences per memory entry. When memory feels bloated, the fix is compression and archiving — never a bigger ceiling. Update existing entries rather than duplicating.

## 2. Preferences

- Be concise and direct. If a word can be cut without losing meaning, cut it.
- Caleb is new to software development. Explain technical concepts with the *why*, not just the *what*.
- Minimal formatting in conversation: prose over bullets unless content is genuinely multifaceted.

## 3. Rules

- Draft and iterate in the temporary outputs folder; only copy finished files into this workspace.
- Never create a separate MEMORY.md or archive.md here — see Section 1.
- Keep this file under 300 lines. Overflow moves to `/resources` with a one-line pointer left behind.
- Apply the Section 1 placement test when adding any rule or fact anywhere in the workspace.
- Distinguish Cowork's installed **Skills** (plugins, auto-triggered) from plain-markdown **skill files** in `/skills` (checklists loaded on request) and from packaged, installable Skills kept in `/claude-skills` (built and benchmarked here, ready for anyone to save). Don't conflate them.
- Log notable findings, surprises, and before/after results to the LinkedIn build log (see Section 5) as they happen — they're content material.
- After a session with a notable token-efficiency or context-quality difference, run the `explain-usage` skill and log a structured entry to `/resources/benefits-log.md` — this is the quantitative evidence base for the public README (see Section 7).

## 4. Routing Map

| If the task involves... | Load this |
|---|---|
| LinkedIn / dev content (drafting, planning posts) | `/workstations/linkedin-content/claude.md` |
| A recurring, no-judgment checklist | The matching file in `/skills` |
| Creating a new workstation | `/resources/creating-new-workstations.md` |
| Questions about the original method | `/resources/jeff-su-cowork-guide.md` |
| Logging a session's token/context benefits | `/resources/benefits-log.md` |
| Installing this method into a new or existing project | `/claude-skills/workstation-bootstrap/SKILL.md` |
| Anything else | This file + built-in memory |

## 5. Workstations

A workstation is a place you work (human judgment required). See `/workstations/README.md`.

- **linkedin-content** — planning and drafting LinkedIn/dev posts about this Cowork build; includes `build-log.md` (raw material)

## 6. Skills

A skill file is a thing Claude does start-to-finish. See `/skills/README.md`.

- **workstation-audit** — checks a workstation for misplaced rules, bloat, and gaps; outputs a findings report

## 7. Claude Skills (published, installable)

`/claude-skills` holds packaged, installable Cowork Skills (`SKILL.md` + assets, buildable into `.skill`) built and tested here — distinct from `/skills`, which holds plain checklists Claude runs on request within this project only. Named for the platform, not the repo, because future non-Claude tooling gets its own sibling folder (e.g. `/other-platform-skills`) rather than mixing in here.

- **workstation-bootstrap** — scaffolds the rules-vs-facts method into any new or existing Cowork project, including migrating an already-bloated one without losing content. Benchmarked at 100% (33/33) on the internal eval suite, up from 60% with no skill. See `/claude-skills/workstation-bootstrap/SKILL.md`.

## 8. References (load on demand only)

- `/resources/jeff-su-cowork-guide.md` — original written guide this setup is based on
- `/resources/creating-new-workstations.md` — read before scaffolding any new workstation
- `/resources/benefits-log.md` — quantitative log of token efficiency, usage, and context-quality results; feeds the public README's Results section
