# LLM Journaling System

An Obsidian-based, agent-assisted journaling system that compiles daily
entries into weekly and monthly reviews—and turns recurring signals into
durable insights, ideas, and operating principles.

## The problem

Daily journaling is relatively easy. The system usually breaks at the
distillation layer: rereading entries, extracting patterns, carrying loose
ends forward, and comparing behavior against priorities.

The LLM Journaling System uses an AI coding agent as a reflective compiler.

## How it works

Daily journals
→ Weekly review
→ Monthly synthesis

Daily journals
→ Promotion candidates
→ Human approval
→ Insights, ideas and principles

## Core design principles

- Local-first markdown
- Obsidian as the markdown interface
- Human-owned context
- Agent-assisted compilation
- Review-gated durable memory
- Targeted rather than exhaustive retrieval
- Git-backed auditability

## Repository structure

[Brief folder explanation]

## Quick start

1. Use this repository as a template or clone it.
2. Open the vault in Obsidian.
3. Customize `vault/context/priorities.md`.
4. Create relevant area and project files.
5. Write daily journals using the template.
6. Run Codex/Claude Code from the repository root.
7. Invoke the weekly or monthly compilation skill.

## Example Codex request

Use the weekly-compilation skill to compile the target week.

Read:
- the daily journals for the week
- priorities.md
- linked project, area and note files

Create:
- a weekly review
- reviewable promotion candidates

Do not modify context files or canonical promotion files.

## Demo

See:
- `examples/demo-input/`
- `examples/demo-output/`

## Privacy

Never make a repository containing real journals public.

See `docs/privacy.md`.

## Project status

Early working release. The workflow has been developed through real use
and is being refined through repeated weekly and monthly compilation runs.

## Inspiration

Inspired by the idea of using LLMs as compilers for personal knowledge,
adapted here into a time-based reflection and human-gated memory system.

## License

MIT