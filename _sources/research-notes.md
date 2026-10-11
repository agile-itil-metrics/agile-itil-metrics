# Research notes

Verified research behind the topics. Rules:

- Record only what was read in a source in the session named, with the source beside it.
- Mark anything unverified as "unverified: do not rely on".
- Verify each Wikipedia slug exists before listing it.

## Model sources (read in the first sessions, October 2026)

- The sibling *Agile ITIL Guide* (`agile-itil-guide`): practices, topic shape, 15-section template, the agile stance. Its own research notes are in its `_sources/research-notes.md`; this book relies on them for the Kanban Guide (v2025.5), the Scrum Guide (November 2020), and the Agile Manifesto principles, and does not repeat them here.
- The sibling *Software Engineering Metrics* (`software-engineering-metrics`): spec shape, metric definitions table, gaming vectors and guardrails, locale and site layout.

## Reference verification pass (11 October 2026)

### URLs

All 33 URLs cited in the references returned HTTP 200 when fetched on 11 October 2026: agilemanifesto.org (three paths), dora.dev (research, metrics guide), github.com/dora-team/fourkeys, google.github.io/eng-practices/review, kanbanguides.org (two paths), martinfowler.com (feature toggles, technical debt quadrant), papers.nips.cc (Sculley et al., 2015), scrumguides.org, sre.google (sre-book chapters and workbook chapters), cisa.gov KEV catalog, finops.org framework, first.org CVSS, gov.uk Service Standard, rfc-editor.org RFC 3339, w3.org WCAG 2.2.

### Corrected after a web search

| Reference | Problem found | Correction |
| --- | --- | --- |
| *The Kanban Guide* | Co-author named as "Raghuvir" and "Orosz"; publisher "Kanban University and Scrum.org" | Authors Vacanti, Yeret, et al.; December 2020; hosted at kanbanguides.org; no publisher claimed. The Scrum.org title is a different document, *Kanban Guide for Scrum Teams* (January 2021). |
| Vacanti, *Actionable Agile Metrics* | Title "for Productivity and Predictability", publisher "ActionableAgile Press" | *Actionable Agile Metrics for Predictability: An Introduction*, self-published (Daniel S. Vacanti, Inc.), 2015 |
| Davidovič, incident metrics | Beyer listed as co-author | Single author: Štěpán Davidovič; O'Reilly report, 2021; also on sre.google |
| *Site Reliability Engineering*, chapter 5 | Authors given as Murphy and Beyer | Chapter "Eliminating Toil" is by Vivek Rau |
| KCS v6 Practices Guide | "2020 edition" | v6 first released 2016 and updated since; the Consortium's page is the current version |
| ITIL service catalogue reference | "Cannon, D. (lead author), Service Strategy and Service Design" | Hunnebeck, L., *ITIL Service Design*, TSO, 2011 |
| Deming, *Out of the Crisis* | "MIT Press, 1982" | MIT Center for Advanced Engineering Study, 1982; MIT Press edition 2000 (catalogs disagree on some dates) |
| Rother and Shook, *Learning to See* | Subtitle "Create Value" in one topic | "Add Value and Eliminate Muda" (the common listing; some catalogs use "Create") |

### Confirmed by a web search

Confirmed that the work exists with the authors, venue, and year given: Choi, Hecht and Tayler (*The Accounting Review* 87(4), 2012, pp. 1135 to 1164); Hubbard, *The Failure of Risk Management*, 2nd edition, Wiley, 2020; Seiden, *Outcomes Over Output* (2019, Sense & Respond Press); Noda et al., "DevEx: What Actually Drives Productivity" (ACM Queue, March to April 2023; volume and issue labels not shown in the results); Forsgren et al., "The SPACE of Developer Productivity" (ACM Queue 19(1), 2021); Dixon, Freeman and Toman (*HBR*, July to August 2010); Parasuraman and Manzey (*Human Factors* 52(3), 2010, pp. 381 to 410); Peng et al. (arXiv 2302.06590, 2023); Shumailov et al. (*Nature* 631, 2024, pp. 755 to 759); Mark, Gudith and Klocke (CHI 2008, pp. 107 to 110); Kruchten, Nord and Ozkaya, *Managing Technical Debt* (Addison-Wesley, 2019).

### Wikipedia

Every Wikipedia link in the topics is resolved by `bin/check --links`. Titles for the Part 11 topics were also checked with HTTP requests when written. `Information_dashboard` and `Make-or-buy_decision` returned 404 and are not used.

### Not independently verified

Everything not listed above. These were cited from memory and reviewed against the maintainer's recollection only: most classic books (Deming, Tufte, Kahneman, Reinertsen, Senge, and similar), most journal articles, the ISO/IEC standard numbers and titles, the NIST publications, the EU regulation numbers, and the ITIL 4 practice guide titles. Treat bibliographic details as leads. The references appendix repeats this caution.

## Open questions

- ITIL 5: the *Agile ITIL Guide* records the owner's own announcements. This book mentions ITIL 4 vocabulary only and does not rely on ITIL 5. Revisit when the owner publishes details.
- AI regulation: statements in Part 10 are dated October 2026 and need rechecking.
