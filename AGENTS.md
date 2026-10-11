# AGENTS.md: operating instructions for AI agents

This repository is a book: *Agile ITIL Metrics*, 88 Markdown topics in 12 parts. It is the metrics companion to the *Agile ITIL Guide* (`~/git/agile-itil-guide/agile-itil-guide`) and follows the spec shape of `~/git/software-engineering-metrics/software-engineering-metrics`.

## The one rule that governs everything

**`spec/index.md` is the source of truth.** Read it first. Where any file disagrees with the spec, the spec wins: fix the file, or change the spec on purpose and bring everything into line in the same commit.

## Orientation

| File | What it is |
| --- | --- |
| `spec/index.md` | Governing specification and golden rules. |
| `spec/structure.md`, `spec/topics.tsv` | The manifest. Keep them in step. |
| `spec/topic-template.md` | The fixed 20-section topic template. |
| `spec/conventions.md` | Style, citation rules, hard rules, layout. |
| `spec/maturity-model.md` | The shared five-level scale. |
| `STYLE_GUIDE.md` | Voice and prompt-writing rules. |
| `tasks.md` | The live checklist. Update it in the same commit as the work. |
| `bin/check` | Quality gates. `--strict` fails on stubs; `--links` resolves Wikipedia links. |
| `bin/scaffold` | Creates missing topic stubs from the manifest. Never overwrites. |
| `bin/build-readme` | Regenerates the README table of contents. |

## Hard rules

1. **Never invent sources, URLs, statistics, survey figures, benchmark values, or quotations.** If you cannot verify it, describe the pattern without the number.
2. **No em-dashes** (U+2014). En-dashes only in numeric ranges.
3. **No stock LLM phrasing** (see `spec/conventions.md`).
4. **Follow the topic template exactly.** Section names, order, and counts.
5. **Every metric gets a gaming vector and a guardrail.**
6. **Metrics describe teams, services, and systems. Never rank individuals.**
7. **Verify every Wikipedia link** before using it. Never guess a slug.
8. **Cross-references carry number and title.**
9. **No real named company in a worked example.** Illustrative numbers are labelled.
10. **Do not reproduce copyrighted framework text** (ITIL, ISO/IEC, Scrum Guide). Summarize and cite.
11. **`.locale-peer-id` files are immutable.**
12. **One writer per file.**
13. **Agile stance.** Emphasize continuous software delivery, continuous collaboration, continuous improvement, and projects built around motivated individuals. De-emphasize sprints, Scrum, burndowns, iterations, and frequent releases (see `spec/index.md`).

## Workflow: write one topic

1. Read the spec files above and the topic's scope in `spec/structure.md`.
2. Read the matching *Agile ITIL Guide* topic and any matching *Software Engineering Metrics* topic; summarize and cite them rather than duplicating.
3. Replace the stub in `locales/en-001/topics/<slug>/index.md`, removing the `<!-- stub -->` marker.
4. Run `bin/check --links`. Fix everything it reports.
5. Run `bin/build-readme`; tick the box in `tasks.md`.
6. Commit.

## Changing the structure

Edit `spec/structure.md` and `spec/topics.tsv` together, run `bin/scaffold`, `bin/build-readme`, and `bin/check`.
