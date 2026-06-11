---
name: monthly-compilation
description: Compile weekly reviews into a strategic monthly review and consolidate promotion candidates using cross-week evidence.
---
# Monthly Compilation

## Purpose

Use this skill to compile one month of weekly reviews into:

1. a draft monthly review in `vault/journals/monthly/`
2. a refined update to `vault/promotion/candidates.md`

This is a higher-level synthesis workflow than weekly compilation.

Its goal is to identify:
- what kind of month this really was
- what repeated across weeks strongly enough to matter
- where behavior aligned or drifted from stated priorities
- which promotion candidates should be confirmed, refined, merged, deferred, or discarded

---

## Inputs

Read the following inputs before drafting outputs:

### Required
- all weekly reviews for the target month, which are located under `vault/journals/weekly/YYYY`. For example, weekly reviews in 2026 are stored in `vault/journals/weekly/2026`.
- `vault/context/priorities.md`

### Use when relevant
- relevant project files under `vault/context/projects`
- relevant area files under `vault/context/areas`
- relevant note file under `vault/context/notes/` 
- existing `vault/promotion/candidates.md`
- canonical promotion files for deduplication awareness only
- previous monthly review, if useful for continuity

Do not expand the scope unnecessarily.
Prefer the smallest relevant context set that improves judgment.

---

## Output Files

This skill produces two outputs:

1. a monthly review draft in `vault/journals/monthly/YYYY`. For example, the monthly review for April 2026 should be stored in `vault/journals/monthly/2026` and follow the naming convention of `Monthly Review @yyyy-mm`.
2. an updated `vault/promotion/candidates.md`

This skill may update `vault/promotion/candidates.md`, but it must not directly update:
- `vault/promotion/insights.md`
- `vault/promotion/ideas.md`
- `vault/promotion/principles.md`
- files under `vault//context`

---

## Core Workflow

### Step 1: Read the month
Read the target month’s weekly reviews and identify:
- recurring wins and supportive conditions
- recurring frictions, drifts, and bottlenecks
- repeated project and area signals
- evidence of alignment or misalignment with stated priorities
- patterns that appear across multiple weeks, not just once

### Step 2: Read current priorities
Read `vault/context/priorities.md` and identify:
- the current season
- relevant monthly priorities
- relevant quarterly priorities
- declared drift or failure modes
- explicitly deferred or non-current focuses

Use this file as the benchmark for alignment.

### Step 3: Pull in relevant context
Read only the project and area files that materially improve interpretation.

Use project notes to understand:
- intended outcomes
- current bottlenecks
- risks and fake progress modes
- strategic significance

Use area notes to understand:
- standards
- current focus
- recurring risks
- positive and negative signals

Read notes under `vault/context/notes/` only when they are explicitly linked in relevant source material or clearly necessary to interpret a repeated pattern, project signal, or area signal at monthly scale.

Use them selectively as supporting evidence or clarification.
Do not expand monthly scope by scanning notes broadly.
### Step 4: Review promotion staging
Read the current `promotion/candidates.md` and assess:
- which candidates now look stronger
- which candidates overlap and should be merged
- which candidates remain weak or thinly evidenced
- whether any higher-order candidate emerges only at monthly scale

Do not treat all prior candidates as valid by default.

### Step 5: Diagnose the month
Form a grounded view of the month.

Answer:
- What kind of month was this, really?
- What moved meaningfully?
- What remained stagnant?
- What repeated strongly enough to matter?
- Where did behavior align with stated priorities?
- Where did it drift?
- What area or project signals stand out at monthly scale?
- Which promotion candidates deserve more confidence, less confidence, merging, or removal?

### Step 6: Draft the monthly review
Generate the monthly review using the monthly review template located in `templates/monthly-review.md`.

Write clearly and diagnostically.
Focus on:
- what defined the month
- what repeated
- what this month revealed more clearly than a single week could
- what should change next month

### Step 7: Refine promotion candidates
Update `vault/promotion/candidates.md` based on monthly evidence.

Use the monthly layer to:
- confirm strong candidates
- refine wording
- merge overlapping candidates
- defer weak ones
- discard stale or unsupported ones
- add new candidates only when they clearly emerge at monthly scale

---

## Promotion Rules

Monthly promotion work is stricter than weekly promotion work.

The monthly layer should prioritize:
- confirmation
- refinement
- consolidation
- pruning

over raw candidate generation.

### Candidate quality bar
A candidate is stronger at monthly scale when it is:
- visible across multiple weeks
- strategically meaningful
- behaviorally actionable
- transferable beyond the immediate month

### Monthly-specific actions
Use the monthly run to:
- raise confidence on well-supported candidates
- lower confidence on weak candidates
- merge duplicate or overlapping items
- sharpen vague candidates into cleaner statements
- discard candidates that no longer look useful

### New monthly candidates
Only add a new candidate if it becomes clear mainly from cross-week synthesis.

Examples:
- a month-long drift pattern
- a repeated area-level sacrifice
- a broader principle that no single week clearly showed
- a strategy or content idea that crystallized across several reviews

### Do not promote
Do not strengthen or add candidates for:
- isolated weekly frustrations
- thin patterns with weak evidence
- generic motivational ideas
- inflated conclusions from a noisy month

---

## Writing Standards

### For the monthly review
Write like a strategic diagnostic memo.

The review should be:
- concise
- comparative
- pattern-aware
- action-oriented

Avoid:
- rehashing daily detail
- merely stacking weekly summaries
- vague self-improvement language
- false precision

### For promotion candidate updates
Be conservative and explicit.

If refining a candidate:
- make it clearer
- make it more evidence-based
- make it easier to route and review

If merging candidates:
- preserve the strongest version
- remove redundant phrasing

---

## Consistency Rules

The monthly review and the candidate updates must agree.

Do not confirm a candidate at high confidence if the monthly review does not support it.

Do not let the monthly review ignore a strong repeated signal that is being promoted.

The monthly promotion stream should feel like a natural consequence of the monthly diagnosis.

---

## Update Boundaries

This skill may:
- create or update the monthly review draft
- create or update `vault/promotion/candidates.md`

This skill must not:
- edit daily journals
- edit weekly reviews except by explicit instruction
- edit files under `vault//context`
- edit canonical promotion files
- silently redefine priorities, projects, or areas

If a context file appears stale or misaligned, note it in the monthly review rather than rewriting it.

---

## Completion Checklist

Before finishing, confirm:

- the monthly review reflects the target month accurately
- priorities were actually used as an alignment benchmark
- repeated patterns were identified across weeks, not just copied from one week
- candidate updates are more selective and refined than weekly outputs
- weak candidates were not preserved automatically
- no canonical promotion files were modified
- no `vault/context` files were modified
- the review and candidate updates are consistent with each other