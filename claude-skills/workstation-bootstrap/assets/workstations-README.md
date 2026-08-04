# Workstations

A workstation is **a place you work**, not a checklist Claude runs alone. Use one when the task needs human judgment and back-and-forth — Claude assists, you make the calls. The test: *is this a place I work, or a thing I do?* Places you work → workstation. Things Claude does the same way every time → `/skills`.

Examples: content planning and review, weekly planning, strategy discussions.

## Structure

Each workstation is a **folder** (not a single file — folders leave room for accumulated context):

```
/workstations/<name>/
  claude.md        # the workstation's instruction set
  resources/       # optional: examples, style guides, reference material
```

Workstation facts and status live in Claude's built-in memory (one memory file per workstation — the cascading pattern), not in files here. Rules live in claude.md. That's the placement test from root CLAUDE.md Section 1.

## Creating one

Ask Claude: "create a workstation for X." Claude follows `/resources/creating-new-workstations.md`, which scaffolds the folder and updates the root routing map, index, and memory.

## Current workstations

- [none yet]
