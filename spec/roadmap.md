# Roadmap, build backlog, and adoption checklists

The authoring backlog for producing and maintaining the book, plus adoption checklists that a team can use to put a metrics program into practice. The live checklist is `tasks.md`; this file is the plan behind it.

Legend: `[ ]` todo, `[~]` in progress, `[x]` done. **(P)** parallelizable.

## Phase 0: Project setup and standards

- [x] Choose the sibling models: `agile-itil-guide` for practices, `software-engineering-metrics` for the spec shape
- [x] Write the specification: index, structure, topic template, conventions, maturity model, locales
- [x] Generate the manifest and `topics.tsv` from one source
- [ ] Add `AGENTS.md`, `AGENTS/` role cards, `CLAUDE.md`, `STYLE_GUIDE.md`
- [ ] Add the special files for public repos (see `special-files-for-public-repos`)
- [ ] Write `bin/check`: manifest agreement, template section order, counts, hard rules, skill links
- [ ] Write `bin/build-readme` and `bin/build-llms`
- [ ] Write `bin/localize` for the English spelling variants
- [ ] Stub every topic directory with `index.md`, `README.md` symlink, and `.locale-peer-id`

## Phase 1: Research and evidence base **(P)**

- [ ] Write `_sources/research-notes.md` from the *Agile ITIL Guide* research notes, then add metrics sources
- [ ] Catalogue the canonical sources per part: Kanban Guide, DORA, SPACE, Google SRE books, ITIL 4 measurement and reporting practice, ISO/IEC 20000, KCS, FinOps Framework
- [ ] Verify the ITIL 5 position against the owner's own publications and date it
- [ ] Decide the overlap policy with `software-engineering-metrics` (summarize and cite instead of duplicating)

## Phase 2: Author Part 1, Foundations of Measurement **(P)**

- [ ] Topics 1.0 to 1.7. Topic 1.2 (Goodhart's law) first, because every other topic cites it.

## Phase 3: Author Part 2, Flow and Continuous Delivery Metrics **(P)**

- [ ] Topics 2.0 to 2.9

## Phase 4: Author Part 3, Service Desk, Incident, and Request Metrics **(P)**

- [ ] Topics 3.0 to 3.7

## Phase 5: Author Part 4, Problem, Change, and Release Metrics **(P)**

- [ ] Topics 4.0 to 4.6

## Phase 6: Author Part 5, Service Level, Availability, and Reliability Metrics **(P)**

- [ ] Topics 5.0 to 5.7

## Phase 7: Author Part 6, Customer and Experience Metrics **(P)**

- [ ] Topics 6.0 to 6.5

## Phase 8: Author Part 7, Asset, Configuration, and Financial Metrics **(P)**

- [ ] Topics 7.0 to 7.7

## Phase 9: Author Part 8, Security, Risk, Compliance, and Supplier Metrics **(P)**

- [ ] Topics 8.0 to 8.5, including the government reporting topic

## Phase 10: Author Part 9, People, Teams, and Improvement Metrics **(P)**

- [ ] Topics 9.0 to 9.6

## Phase 11: Author Part 10, Metrics in the Age of AI **(P)**

- [ ] Topics 10.0 to 10.5

## Phase 12: Author Part 11, Building a Metrics Program

- [ ] Topics 11.0 to 11.5

## Phase 13: Appendices

- [ ] 12.1 Glossary
- [ ] 12.2 Metric definitions and formulas reference (assembled from the topics)
- [ ] 12.3 Checklists
- [ ] 12.4 Templates (metrics charter, metric card, dashboard spec, review agenda)
- [ ] 12.5 Maturity self-assessment
- [ ] 12.6 References and further reading
- [ ] 12.7 Index

## Phase 14: Skills, site, and release

- [ ] Write `skills/agile-itil-metrics-skill` for readers and `skills/agile-itil-metrics-maintainer-skill` for maintainers; copy other skills unchanged from `~/git/skills-on-ai/skills-on-ai/skills`
- [ ] Build the SvelteKit site following the sibling project's architecture
- [ ] Technical review by subject-matter experts per part
- [ ] Cross-topic consistency pass: terminology, cross-references, overlap with the guide
- [ ] Confirm the gaming vector and guardrail appears in every metric topic
- [ ] Verify all citations, links, and standards references
- [ ] Beta-read with target audiences: a service desk team, an agile team running a live service, a government IT group
- [ ] First translated locale (`cy-gb`)

## Adoption checklists for a team

### First 30 days: start where you are

- [ ] Pick one service and one team. Write down why you want to measure.
- [ ] List the data you already have in your ticketing and delivery tools.
- [ ] Choose at most five metrics: one flow, one stability, one service level, one experience, one health.
- [ ] For each, write the definition card: clocks, exclusions, data source, owner, gaming vector, guardrail.
- [ ] Show the team the raw data before any dashboard exists.

### Days 30 to 90: make it routine

- [ ] Review the metrics in an existing team event, not a new meeting.
- [ ] Show distributions and trends, not single numbers or league tables.
- [ ] Record each decision a metric changed, and each metric that changed nothing.
- [ ] Retire a metric that nobody used.

### Days 90 to 180: connect and scale

- [ ] Add the second team. Reconcile definitions only where roll-up matters.
- [ ] Link flow and change measures to service level and experience measures.
- [ ] Agree what leadership sees, and what stays with the team.
- [ ] Run a gaming review: how would we cheat this, and would we notice?
- [ ] Reassess maturity with the shared five-level scale.
