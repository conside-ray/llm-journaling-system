---
name: weekly-compilation
description: Compile one week of daily journals into a diagnostic weekly review and reviewable promotion candidates.
---
# Weekly Compilation

## Purpose

Use this skill to compile one week of daily journals into:

1. a draft weekly review in `vault/journals/weekly/`
2. a reviewed set of promotion proposals in `vault/promotion/candidates.md`

This is a single analysis workflow with two output streams.

The goal is not just to summarize the week, but to identify:
- what actually mattered
- what moved and what stalled
- where behavior aligned or drifted from stated priorities
- which signals may deserve durable promotion

---

## Inputs

Read the following inputs before drafting outputs:

### Required
- All daily journals for the target week. For example, the daily journals from April 2026 will be saved under `vault/journals/daily/2026/2026-04`. The naming of each daily journal file follows this format: `Daily Journal @YYYY-MM-DD`. Unless otherwise specified, a target week refers to the past week from Monday to Sunday. For example, if the human initiates a weekly compilation on Monday, 2026-04-27, the target week would be Monday, 2026-04-20 to Sunday, 2026-04-26. There may be missing days from the past week, so use any available daily journals from that week as input. 
- `vault/context/priorities.md`

### Use when relevant
- project files referenced in the week’s tasks or notes
- area files referenced directly or clearly implicated by the week’s content
- note files referenced directly in the week's content
- when explicitly referencing a project/area/note, the human will use this format: `@[[example project/area/note]]` in daily journals
- the previous weekly review, if useful for continuity

Do not expand scope unnecessarily.  
Prefer the smallest set of relevant context files that improves interpretation.

---

## Output Files

This skill produces two outputs:

1. a weekly review draft in `vault/journals/weekly/`
2. an updated `vault/promotion/candidates.md`

This skill may update `vault/promotion/candidates.md`, but it must not directly update:
- `vault/promotion/insights.md`
- `vault/promotion/ideas.md`
- `vault/promotion/principles.md`
- files under `vault/context`

---

## Core Workflow

### Step 1: Read the week
Read the target week’s daily journals and identify:
- intended focuses and must-dos
- actual progress and unfinished work
- recurring thoughts, frictions, and emotional signals
- notable task-to-project links
- signs of drift, avoidance, momentum, or bottlenecks

### Step 2: Read current priorities
Read `vault/context/priorities.md` and identify:
- the current season
- current monthly priorities
- relevant quarterly priorities
- declared drift or failure modes
- anything explicitly marked as not current

Use this file as the benchmark for alignment.

### Step 3: Pull in relevant context
Read only the project and area files that are materially helpful for interpreting the week. Also read notes under `vault/context/notes/` only when they are explicitly linked in the target week’s daily journals or clearly necessary to interpret a directly referenced project or area.

Use project files to understand:
- intended outcomes
- current bottlenecks
- fake progress risks
- next moves

Use area files to understand:
- standards
- current focus
- recurring risks
- negative and positive signals

Use notes as supporting context, not as a default source set.  
Do not widen scope by scanning unrelated notes.

### Step 4: Diagnose the week
Form a grounded view of the week.

Answer:
- What actually mattered this week?
- What moved meaningfully?
- What remained stagnant?
- What dragged or repeated?
- Where did behavior align with stated priorities?
- Where did behavior drift?
- What project or area signals stand out?
- What, if anything, may deserve durable promotion?
- When a linked note contains reusable reasoning, frameworks, or conclusions relevant to the week, use it to improve interpretation and surface any distillable insights, ideas, or principles.

### Step 5: Draft the weekly review
Generate the weekly review using the weekly review template located at `templates/weekly-review.md`.

Write clearly and diagnostically.
Prefer concrete observations over vague uplift.
Focus on:
- what mattered
- what changed
- what repeated
- what should carry into next week

The weekly review draft finished by the agent should be saved under `vault/journals/weekly/YYYY`. For example, any weekly reviews for 2026 should be saved under `vault/journals/weekly/2026`. And the file should be renamed properly. For example, for the review of the 20th week of 2026, name it as `Weekly Review @2026-20.md`.

### Step 6: Generate promotion candidates
From the same analysis pass, identify a small number of strong promotion candidates.

Use `vault/promotion/candidates.md` as a staging file and fill in any fields relevant to the week. 
Do not promote directly into canonical promotion files.

Candidates should be selective and evidence-based.

`vault/promotion/candidates.md` should contain only new, deferred, rejected, or pending-review items for the current review period. Do not keep already-approved canonical memories rolling forward as full candidate entries. When an existing canonical insight, idea, or principle is materially reinforced by the week, mention it briefly in the weekly review or in a compact "Canonical Reinforcements" note with 0-3 bullets, but do not restage it as a candidate unless there is a concrete review action attached.

---

## Promotion Rules

Generate promotion candidates only when they appear useful beyond the current week. 

A candidate is stronger when it is:
- recurring
- actionable
- strategically relevant
- transferable beyond one day or one week

### Candidate types
Use only these destination types:
- insight
- idea
- principle

### Insight candidates
Use for:
- recurring behavioral patterns
- emotional or energy patterns
- repeated frictions or supportive conditions
- durable self-observations

### Idea candidates
Use for:
- content ideas
- product or workflow ideas
- research questions
- business or strategy seeds worth developing later

### Principle candidates
Use for:
- decision rules
- operating heuristics
- behavior-guiding rules that appear reusable

### Do not promote
Do not generate candidates for:
- one-off moods
- generic motivational lines
- obvious facts with no future leverage
- identity-level conclusions based on thin evidence
- elegant wording without operational value

### Candidate count
Be selective.

Normally generate:
- 0–3 insight candidates
- 0–2 idea candidates
- 0–2 principle candidates

Fewer is better than padding.

---

## Writing Standards

### For the weekly review
Write like a clear internal memo.

The review should be:
- concise
- grounded
- diagnostic
- action-oriented

Avoid:
- therapy-style language
- vague praise
- productivity clichés
- inflated certainty

### For promotion candidates
Each candidate should be:
- clearly stated
- evidence-backed
- easy to review
- written close to how it would appear in the destination file

Use confidence levels conservatively.

---

## Consistency Rules

The weekly review and promotion candidates must agree.

Do not let promotion candidates contradict the weekly diagnosis.

If a pattern is too weak to mention confidently in the weekly review, it is usually too weak to promote.

Promotion candidates should emerge naturally from the same analysis that shaped the weekly review.

---

## Update Boundaries

This skill may:
- create or update the weekly review draft
- create or update `vault/promotion/candidates.md`

This skill must not:
- edit daily journals
- edit files under `vault/context`
- edit canonical promotion files
- silently redefine priorities, projects, or areas

If a context file appears stale or inconsistent, note this in the weekly review or review notes rather than rewriting it.

---

## Completion Checklist

Before finishing, confirm:

- the weekly review reflects the target week accurately
- stated priorities were actually compared against behavior
- meaningful project and area signals were surfaced when relevant
- promotion candidates are selective and evidence-based
- no canonical promotion files were modified
- no `vault/context` files were modified
- the two outputs are consistent with each other
