# LLM Journaling System

An Obsidian-based, agent-assisted journaling system that compiles daily entries into weekly and monthly reviews, and proposes the insights, ideas, and operating principles worth keeping. Promotion happens only after a person reviews the candidates.

**Ray Kwan.** I built this and have used it since April 2026. The public repository holds the workflow and a synthetic demo.

## Why I built this

Daily notes were easy to keep. Weekly and monthly reviews were not, so a week could pass without anything useful being captured from it.

The biggest value isn't time saved. I finally have a working system that cuts the friction of actually doing those reviews, and that captures the insights and action items they distill. The difference is whether a week or month is really well lived and recorded, or just slips away.

## The problem

The usual break is the distillation layer: rereading entries, extracting patterns, carrying loose ends forward, and comparing what happened with stated priorities.

A coding agent does that pass. Context stays human-owned. Durable memory changes only when a person approves a candidate.

## How it works

Daily journals → weekly review → monthly synthesis

Daily journals → promotion candidates → human approval → insights, ideas, and principles

On a weekly run the agent reads that week's daily journals, `vault/context/priorities.md`, and the project, area, and note files the week actually links. It drafts a review in `vault/journals/weekly/` and updates `vault/promotion/candidates.md`. Context files and the canonical promotion files stay unchanged.

A monthly run does the same from that month's weekly reviews, using `skills/monthly-compilation/`.

## The same pattern at work

Raw daily inputs become an AI-compiled periodic review. A human approves what gets promoted into durable knowledge.

Meeting notes can become a weekly ops review. Customer-call notes can become a monthly insight digest.

## Demo

Five synthetic journals, 1–5 June 2026, live in [`examples/demo-input/`](examples/demo-input/). The input has no priorities file, and the review says alignment cannot be judged.

Friday, 5 June ([`Daily Journal @2026-06-05`](examples/demo-input/journals/daily/Daily%20Journal%20@2026-06-05.md)):

> Energy 4/5. Mood: Blocked. "It's nice that you finished all the assigned tasks today. But at the same time, you had a clearer feeling that something was stopping you from achieving more."

From [`Weekly Review @2026-23`](examples/demo-output/Weekly%20Review%20@2026-23.md):

> Planned tasks were completed consistently, and the week moved from preparation into more active job-search execution. The unresolved issue is that completing assigned tasks did not remove the feeling of being blocked, suggesting a need to identify the actual throughput constraint rather than simply adding more tasks.

Carry forward from the same review:

> - Start building the job-hunting agent, beginning with one bounded workflow that can be tested against real applications.
> - Record outcomes from the interview, HR follow-up, and five screened jobs so the job-search process can be evaluated by conversion and learning, not task completion alone.
> - Identify what specifically felt blocked on Friday: application volume, role fit, workflow friction, uncertainty, or another constraint.

One staged candidate from [`promotion-candidates.md`](examples/demo-output/promotion-candidates.md):

> ### Task completion can conceal an unresolved bottleneck
>
> - Proposed destination: `promotion/insights.md`
> - Candidate: Completing assigned tasks does not necessarily mean the highest-leverage constraint is being addressed; a sense of blockage after a fully completed day is a signal to inspect outcomes and bottlenecks.
> - Evidence: On June 5, all assigned tasks were completed, but the journal still reported a clear feeling that something was preventing greater progress.
> - Confidence: Medium. The contrast is concrete, but the underlying bottleneck has not yet been identified.
> - Status: Pending review

The same file also proposes an idea (validate one job-hunting agent workflow before expanding it) and a principle (treat rejection as information about fit), each with evidence and a confidence level.

## Quick start

1. Clone the repository and open `vault/` in Obsidian.
2. Edit `vault/context/priorities.md`. Add project, area, and note files from `templates/` for the work you want in scope.
3. Write daily journals from `templates/daily-journal.md` into `vault/journals/daily/`.
4. From the repository root, run a coding agent such as Codex or Claude Code and invoke `skills/weekly-compilation/` or `skills/monthly-compilation/`.

```text
Use the weekly-compilation skill to compile the target week.

Read:
- the daily journals for the week
- vault/context/priorities.md
- linked project, area, and note files

Create:
- a weekly review
- reviewable promotion candidates

Do not modify context files or canonical promotion files.
```

## Design principles

- Local-first markdown
- Obsidian as the markdown interface
- Human-owned context
- Agent-assisted compilation
- Review-gated durable memory
- Targeted rather than exhaustive retrieval
- Git-backed auditability

## Repository

```text
skills/weekly-compilation/    one week of journals → review + candidates
skills/monthly-compilation/   one month of weekly reviews → monthly review + candidates
templates/                    daily journal, weekly review, monthly review, project, area, note
vault/context/priorities.md   current priorities; human-owned
vault/promotion/              candidates.md is agent-writable; insights, ideas, and principles are canonical
vault/journals/               created in use: daily/, weekly/, monthly/
examples/demo-input/          five synthetic daily journals, 2026-06-01 to 2026-06-05
examples/demo-output/         Weekly Review @2026-23 and promotion-candidates.md
docs/privacy.md               what not to put in a public repo
AGENTS.md                     repository rules for the agent
```

## Privacy

This repository contains synthetic examples only. Keep real journals in a private repository.

See [`docs/privacy.md`](docs/privacy.md).

## License

[MIT](LICENSE)
