---
name: workstation-bootstrap
description: Bootstrap a brand-new Claude Cowork project with the rules-vs-facts Workstations method (Jeff Su's Cowork method, adapted) — scaffolds a lean CLAUDE.md, /workstations, /skills, and /resources folders, and seeds the project's built-in memory. Use this whenever the user starts a new project or switches to a new topic and wants it structured — phrases like "set up this project", "bootstrap this project", "apply my workstations method", "new topic, new project", "give this project a CLAUDE.md", "set this up like my Workstations project", or any request to organize a fresh Cowork project so context stays lean across sessions. Also use when the user asks to migrate an existing unstructured project onto this method.
---

# Workstation Bootstrap

Scaffold the rules-vs-facts method into a fresh Cowork project so every future session there starts with lean, auto-loaded context instead of a growing chat history. Also handles migrating an existing, bloated project onto the method (see "Migrating an existing project" below).

## The method in one paragraph (why this exists)

Long-running chats degrade: every turn re-carries the whole history until the context window fills and the user must start over and re-explain. This method splits durable context into two layers by *rate of change*. Stable, prescriptive rules ("always/never", "before X do Y") go in a root `CLAUDE.md` that auto-loads every session — same small token cost in session 100 as in session 1. Changeable facts (status, decisions, current focus) go in Claude's built-in persistent memory. A routing map in `CLAUDE.md` points to task-specific files that load only on demand. Result: a fresh chat is never blind, and no file grows without bound.

## The primary quality test (applies to everything below)

The real objective is not a line count — it is that **every line of the always-loaded `CLAUDE.md` earns its place**: each line must be either prescriptive (a rule) or routing (a pointer). Any changeable fact found in `CLAUDE.md` is a defect, regardless of how short the file is. Line guidance (start ~60–80, hard ceiling 300) exists as a backstop against slow bloat, not as the goal — never pad toward a target, and never judge a dense-but-all-prescriptive file as too long against an arbitrary bar. When trimming is needed, fix it by relocating content (facts → memory, task detail → `/resources`), not by deleting substance.

## Step 1 — Interview first

A fresh project means you know nothing about the topic yet. Before writing anything, ask (use AskUserQuestion if available; keep it to one round):

1. **What is this project?** One or two sentences of purpose — this seeds the memory file and CLAUDE.md header.
2. **First workstation(s)?** A workstation is *a place you work* — collaborative, human-judgment-required (content planning, strategy, experimentation). Ask what ongoing area of work they'll start with. It's fine to start with one, or zero.
3. **Any known repeatable processes?** Those become `/skills` checklist files — *things Claude does* the same way every time. Don't invent any; only scaffold what the user names.
4. **Optional extras — default all to *no* unless asked** (a bootstrap should start minimal):
   - a public-facing README (if they may share the repo);
   - git guidance (if they want version tracking);
   - **measurement** — if the user wants evidence of what the method buys them (token savings, context quality), scaffold `resources/benefits-log.md` from `assets/benefits-log-template.md` and add one rule to `CLAUDE.md`: after a session with a notable token or context-quality difference, log a structured entry there. Offer this one proactively when the user has mentioned documenting, sharing, or proving the method — an uninstrumented project is a lost data source, and the log is how the method's value stops being anecdotal.

Confirm there is a connected project folder to write into. If none is connected, ask the user to connect one before proceeding.

## Step 2 — Scaffold the files

Copy each template from `assets/`, tailor the bracketed placeholders to the interview answers, and write into the project root:

| Template | Destination | Notes |
|---|---|---|
| `assets/CLAUDE-template.md` | `CLAUDE.md` | Tailor Sections 2, 4, 5, 6 to the interview. Delete rows/sections that don't apply yet — lean beats complete. |
| `assets/workstations-README.md` | `workstations/README.md` | Update "Current workstations" list. |
| `assets/skills-README.md` | `skills/README.md` | Update "Current skills" list (may be empty). |
| `assets/creating-new-workstations.md` | `resources/creating-new-workstations.md` | Copy verbatim — it's method reference, not project-specific. |
| `assets/benefits-log-template.md` | `resources/benefits-log.md` | Only if the user opted into measurement (Step 1). |

For each workstation named in the interview, scaffold `workstations/<name>/claude.md` following the structure in `resources/creating-new-workstations.md` (folder, not single file — folders leave room to grow), and add its routing-map row and Section 5 line in `CLAUDE.md`.

Important tailoring rules:

- **Do not import content from other projects.** Rules that belong to the project this method was first built in are project-specific facts of *that* project, not part of the method. Only the structure and the placement test travel.
- **Apply the primary quality test** — all-prescriptive-or-routing — as you write, not after.
- **Draft in a temporary location only when the folder has existing content** (migrations, partial setups) — never leave a user's real folder half-migrated. For a fresh, empty project, scaffold in place: there is nothing to disturb, and double-writing every file wastes tokens.

## Migrating an existing project

When the project already has content — typically a bloated CLAUDE.md, an overstuffed Instructions field, or both — the goal changes from *creating* structure to *relocating* content into it without loss. Work in this fixed order, because it fails safest: if the migration is interrupted partway, the most important content has already been handled.

1. **Safety-critical rules first.** Anything whose violation causes real harm (legal claims, confidentiality, hard business floors) moves to the new `CLAUDE.md` before anything else is touched.
2. **Durable preferences and conventions next** — the rest of the prescriptive content.
3. **Task-specific workflows out** — processes and reference material go to `/skills` (repeatable checklists) or `/resources` (reference), each with a routing-map pointer. A workflow is not a workstation: workstations are folders for ongoing human-judgment areas only, and it is normal for a migration to produce just one workstation, or none.
4. **Facts last** — statuses, prices, in-progress work go to the memory staging file (Step 3). Historical logs (old weekly updates and the like) go to a `/resources` archive file — preserved verbatim, out of the always-loaded path.

Migration rules:

- **Never fabricate.** If the original says "in May" with no year, the migrated content says "in May" with no year. Do not resolve ambiguity by inventing dates, names, numbers, or reasons — flag genuine ambiguities to the user instead. Migration moves information; it must not manufacture it.
- **Nothing disappears silently.** Every piece of the original must be findable afterward — in the new CLAUDE.md, a `/skills` or `/resources` file, the archive, or the staging file — or explicitly listed to the user as proposed-for-deletion. "Don't lose anything important" is the promise; the user, not you, decides what's unimportant.
- **Always address the Instructions field.** If the user duplicated content into the project's Instructions box, tell them explicitly — in the new CLAUDE.md's load note *and* in your final report — to empty it, and why (double loading costs tokens every session and is often the main cause of "chats got slow").
- Judge the result by the primary quality test, not by percentage shrunk: the always-loaded file should contain only rules and routing. A migration that moves every fact out has succeeded even if the rule set itself is substantial.

## Step 3 — Stage facts, then seed memory

Facts must never exist *only* in memory during bootstrap — if memory seeding fails, is skipped, or the user abandons setup partway, those facts would be stranded outside the project. So:

1. **Stage first:** write all facts destined for memory to `resources/memory-staging.md` inside the project — purpose, bootstrap date, current focus, and (for migrations) every relocated fact: statuses, pricing, in-progress work. Head the file with one line explaining what it is: a temporary holding file whose contents belong in built-in memory, deletable once memory is verified.
2. **Then seed:** create one memory file for the project from the staging content (cascading pattern: one file per project, root index holds one line), and add a one-line entry to the memory index. Apply the placement test as you write — anything prescriptive belongs in `CLAUDE.md` instead.
3. **Delete staging only after verification** (Step 4) confirms both the CLAUDE.md load path *and* that memory holds the facts. Until then the staging file stays, and your report says so. If the environment has no persistent-memory tools, say so plainly, keep the staging file as the facts' home, and note in `CLAUDE.md` Section 1 where facts live so future sessions don't hunt for a memory that isn't there.

## Step 4 — Verify the load path

Tell the user, in plain language:

- The project's **Instructions field must stay empty** — `CLAUDE.md` auto-loads every session, and pasting it into Instructions would load it twice (double token cost). This is a known trap.
- How to verify: in the *next* new chat in this project, ask "what are this project's standing rules?" — if Claude answers from `CLAUDE.md` without being pointed at it, the load path works. Record the verification result in the project's memory file — and once memory is confirmed holding the staged facts, `resources/memory-staging.md` can be deleted.

## Step 5 — Self-audit before reporting

Before telling the user you're done, verify your own output against this checklist. Every item is mechanically checkable; fix any failure before reporting rather than mentioning it as a caveat. This exists because these are precisely the conventions that drift when scaffolding is done from general knowledge — catching them now costs seconds; catching them at audit time costs a cleanup session.

Audit from your working state, not by re-reading everything: you just wrote these files, so verify structure with cheap targeted checks (an `ls`, a grep) and only re-read content you did *not* write this session — pre-existing files in a migration, for example. The audit's value is in the checking, not the re-reading; re-reading your own fresh output roughly doubles its cost for nothing.

- Every workstation is a **folder** under `workstations/` containing a `claude.md` — no bare `<name>.md` files, no `WORKSTATION.md`.
- Every skill is a **plain-markdown checklist** directly in `skills/` — not a `.claude/skills/` plugin layout, not a `processes/` folder, no YAML frontmatter.
- Every routing-map row in `CLAUDE.md` points at a file that exists, and every workstation/skill on disk has its routing-map row and index line.
- `CLAUDE.md` passes the primary quality test: no changeable facts anywhere in it.
- Nothing exists that the user didn't ask for: no project README, benefits log, or git setup unless requested (workstations/skills folder READMEs from the templates are part of the method and fine).
- `resources/memory-staging.md` exists and holds every fact that was routed to memory.
- For migrations: spot-check the no-fabrication rule (dates, names, numbers match the original) and confirm every original section is findable in the output.

## Step 6 — Report

Close with a short summary: what was scaffolded, where facts vs rules now live, the self-audit result, and the one-sentence habit that keeps the system healthy — *when adding any note, ask: rule or fact? Rule → CLAUDE.md. Fact → memory.* Remind the user that bloat is fixed by relocating and archiving, never by raising a ceiling — and, for migrations, that the Instructions field needs emptying if it held duplicated content.

## Placement test (the core rule — apply everywhere)

- Prescriptive ("always/never", "before X do Y") → `CLAUDE.md` or a workstation `claude.md`
- A fact that could change (status, tools in use, current focus) → built-in memory
- Task-specific instructions Claude needs only sometimes → a `/resources` file plus a one-line routing-map pointer

## Workstation vs. skill test

*Is this a place I work, or a thing I do?* Ongoing area needing human judgment and back-and-forth → workstation. Repeatable process run the same way every time → a plain-markdown checklist in `/skills`. Neither of these is a Cowork installed Skill (plugin) — keep the three concepts distinct, and say so if the user conflates them.
