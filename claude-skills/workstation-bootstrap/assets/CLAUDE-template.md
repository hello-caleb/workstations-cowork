# CLAUDE.md

Root instruction set for the [PROJECT NAME] workspace (rules-vs-facts method). Hard ceiling: 300 lines; start lean (~60–80) and let rules earn their place. Task-specific content lives in `/workstations`, `/skills`, or `/resources` — not here.

**Load note:** Cowork auto-loads this file every session. The project's Instructions field stays empty — do not paste content there, or it will load twice. Verify auto-load in the first new chat and record the result in memory.

---

## 1. Memory System

Claude uses its built-in persistent memory (individual typed files + auto-loaded index), not separate MEMORY.md/archive.md files in this workspace. Cascading pattern: one memory file for this project (plus one per workstation as they mature); root index holds one line each.

**Placement test (apply to every entry):**
- Prescriptive ("always/never", "before X do Y") → belongs in this file or a workstation claude.md
- A fact that could change (status, tools in use, current focus) → belongs in built-in memory

**Entry hygiene:** 1–2 sentences per memory entry. When anything feels bloated, the fix is compression and archiving — never a bigger ceiling. Update existing entries rather than duplicating.

## 2. Preferences

- [USER PREFERENCES — e.g. conciseness, explanation depth, formatting. Copy only preferences the user actually stated.]

## 3. Rules

- Draft and iterate in the temporary outputs folder; only copy finished files into this workspace.
- Never create a separate MEMORY.md or archive.md here — see Section 1.
- Keep this file under 300 lines. Overflow moves to `/resources` with a one-line pointer left behind.
- Apply the Section 1 placement test when adding any rule or fact anywhere in the workspace.
- Distinguish Cowork's installed **Skills** (plugins, auto-triggered) from plain-markdown **skill files** in `/skills` (checklists loaded on request). Don't conflate them.
- Continuity: at natural pause points in a working session, update this project's memory file with current state — what's done, what's next, open decisions. This keeps a standing handoff, so any new chat resumes with just "pick up where we left off."
- Long chats degrade model quality well before the context window is full ("context rot"). If this chat has gone long or quality is drifting — forgotten constraints, repeated corrections — say so proactively, checkpoint state to memory, and suggest the user start a fresh chat. Fresh chats are cheap here by design; err on the side of handing off.
- [PROJECT-SPECIFIC RULES — only ones the user stated. Delete this line if none.]

## 4. Routing Map

| If the task involves... | Load this |
|---|---|
| [FIRST WORKSTATION TOPIC] | `/workstations/[name]/claude.md` |
| A recurring, no-judgment checklist | The matching file in `/skills` |
| Creating a new workstation | `/resources/creating-new-workstations.md` |
| Anything else | This file + built-in memory |

## 5. Workstations

A workstation is a place you work (human judgment required). See `/workstations/README.md`.

- **[name]** — [one-line purpose. Delete section content if no workstations yet.]

## 6. Skills

A skill file is a thing Claude does start-to-finish. See `/skills/README.md`.

- [none yet]

## 7. References (load on demand only)

- `/resources/creating-new-workstations.md` — read before scaffolding any new workstation
