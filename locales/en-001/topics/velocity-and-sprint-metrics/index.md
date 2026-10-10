# Velocity and sprint metrics

**Velocity is a planning aid that belongs to one team and one backlog, so use it to forecast what that team can finish, pair it with sprint goal success and a quality measure, and never use it to compare teams or judge people.**

## Overview and motivation

[Scrum](https://en.wikipedia.org/wiki/Scrum_(software_development)) is an agile framework in which a team works in short, fixed-length cycles called [sprints](https://en.wikipedia.org/wiki/Sprint_(software_development)), usually one to four weeks long. At the start of each sprint the team forecasts what it can finish, and at the end it inspects the result with stakeholders. Most teams that use sprints also keep a handful of numbers about them. This topic covers those numbers: what they tell you, what they hide, and how they behave once people start to care about them.

The best known of these numbers is [velocity](https://en.wikipedia.org/wiki/Velocity_(software_development)). Velocity is the amount of work a team completes in a sprint, most often expressed in [story points](https://en.wikipedia.org/wiki/Story_point). A story point is a relative unit of size that a team assigns to a backlog item, combining effort, complexity, and uncertainty. Teams often assign points together by [planning poker](https://en.wikipedia.org/wiki/Planning_poker), a technique in which each member privately chooses an estimate and the group discusses differences. The unit has no meaning outside the team that uses it. Two points on one team is not the same amount of work as two points on another, and that fact drives most of the advice that follows.

The 2020 edition of the Scrum Guide, written by Ken Schwaber and Jeff Sutherland, defines the sprint, the Sprint Goal, and the Sprint Backlog. It does not prescribe story points or velocity. Both came into common use through practices such as Extreme Programming and through books on agile estimation, and many teams adopted them as habits around Scrum rather than as parts of it. That origin matters, because it means the number is a tool a team chose for itself. When someone outside the team starts to depend on it, the tool changes character.

Four ideas carry most of the advice in this topic.

- **Velocity is a forecasting input.** It answers "roughly how much can we take on next sprint?" using what happened in recent sprints. It is a range based on history, not a promise and not a score.
- **Sprint goal success is an outcome signal.** The Sprint Goal is the single objective for the sprint. Whether the team met it says more about value than how many points moved to done.
- **Forecast accuracy is a trust signal.** If the team consistently finishes about what it said it would, stakeholders can plan around it. If it swings widely, the cause is worth a conversation.
- **Context decides the reading.** A sprint disrupted by an incident, an audit, or an unplanned production fix will show low velocity for reasons that have nothing to do with effort or skill.

### How the agile and ITIL views differ

The agile view treats a sprint as a learning loop: plan, build, inspect, adapt. The measures are inward facing, meant to help one team. The ITIL view, in ITIL 4 (the version published by AXELOS and now owned by PeopleCert), is organized around the service value chain and a set of practices. ITIL does not define velocity. It does describe practices where sprint-style work lands: change enablement for what is released, incident management and problem management for the interrupts that disturb the plan, and continual improvement for acting on what the measures show. ITIL itself is described in the encyclopedia article on [ITIL](https://en.wikipedia.org/wiki/ITIL).

A team that builds and runs a service sits in both views at once. Its sprint has planned improvement work and also a stream of unplanned operational work. If velocity ignores that second stream, the number looks poor in a sprint with many incidents and the team gets blamed for something the measure never captured (see topic 2.9, Operational work and unplanned work). Good practice is to show planned and unplanned work together and to describe the sprint honestly.

## Key principles

- **Velocity belongs to one team.** Points are relative to a team's own shared understanding. Compare a team with its own past, never with another team.
- **Use ranges, not single numbers.** Forecast from the spread of recent sprints, for example the lowest, median, and highest of the last several, rather than from one best or latest result.
- **Count done work only.** An item is counted when it meets the team's definition of done. Partial credit inflates the number and hides carryover.
- **Pair speed with value and quality.** Velocity with sprint goal success, and both with escaped defects or rework, so that a rise in one cannot hide a fall in another.
- **Protect the estimate from the measure.** Once points are rewarded, estimates drift upward. Keep the number out of performance conversations and out of targets.
- **Show the interrupts.** Planned and unplanned work belong on the same view, so the team's real capacity is visible to the people who set expectations.
- **Describe teams and sprints, never individuals.** Points per person is a vanity figure and a trust breaker.

## Metric definitions

Each metric below belongs to a single team and a single backlog. "Done" means the item met the team's written definition of done by the end of the sprint. Sprint boundaries are the planned start and end times of the sprint. Items that were not in the sprint backlog on the first day are counted as added scope.

| Metric | Definition | Formula | Unit | Data source | ITIL practice | Agile counterpart | Cadence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Velocity | Story points of items that met the definition of done within the sprint | sum of points of items done by the sprint end; clock runs from sprint start to sprint end; items done after the end, and partially done items, count as zero | story points per sprint | Issue tracker, sprint report | Continual improvement; change enablement (as the capacity behind planned change) | Velocity as a forecasting input in sprint planning | Each sprint, reviewed with a rolling window of recent sprints |
| Sprint goal success rate | Share of sprints in a window in which the team judged the Sprint Goal met at the sprint review | sprints with the goal met / sprints in the window; judged at the sprint review, with the criterion written at sprint planning | percent | Sprint planning and review notes | Continual improvement; service level management (when the goal protects a service commitment) | Sprint Goal and sprint review | Each sprint, trended quarterly |
| Forecast reliability | How closely the work done matches the work the team forecast at sprint planning | points (or items) of forecast items done by sprint end / points (or items) forecast at the end of planning on day one; excludes added scope | percent | Issue tracker snapshot at sprint start and end | Continual improvement; service level management | Sprint forecast and the Sprint Backlog | Each sprint; shown as a range over recent sprints |
| Carryover rate | Share of forecast items not done at the sprint end and moved into a later sprint | items forecast and not done by sprint end / items forecast; counts an item once per sprint it is carried | percent | Issue tracker sprint history | Problem management (for repeated causes); continual improvement | Sprint retrospective; definition of done | Each sprint |
| Mid-sprint scope change | Work added to or removed from the sprint after day one, with the reason | items (or points) added after day one plus items removed after day one, tagged planned change, incident, or request; excludes edits to the wording of an item | count of items and points | Issue tracker change log | Incident management; change enablement; service request management | Sprint Backlog negotiation with the Product Owner | Each sprint |
| Sprint throughput | Number of work items done in the sprint, regardless of size | count of items that met the definition of done between sprint start and end; excludes items closed as won't do | items per sprint | Issue tracker | Continual improvement | Flow throughput as a size-free forecasting input | Each sprint |

Velocity and throughput measure the same sprint in two units. Throughput needs no estimates, so it is harder to inflate, but it treats a small item and a large one as equal. Flow measures that need no sprints are in topic 2.1, Kanban flow measures.

The clocks matter. "Done" must be judged at the sprint end against the definition of done, not at the moment someone declares an item finished in a meeting. If testing or release approval sits outside the sprint, the metric reports work that is not yet usable by customers, and the definition of done needs to say so.

## Recommendations

### Use velocity for its one job

**1. Treat velocity as a forecast input, not a performance measure.** Use the last several sprints to give the Product Owner a range of what the team is likely to complete. State the range and the spread in sprint planning, for example "between X and Y points, most often near Z". The number answers a planning question for the team that owns it. It does not say whether the team is doing well.

**2. Keep points and velocity private to the team and its direct stakeholders.** Roll-ups of points across teams, or velocity targets handed down from above, invite inflation. If leadership needs a delivery view, offer sprint goal success and the flow measures instead (see topic 2.1, Kanban flow measures). If someone insists on a cross-team number, convert to something the teams share, such as items done or the outcome each team delivered.

**3. Never compare velocity across teams.** Points are calibrated by each team to its own work, tools, and shared language. A team with a velocity of 40 is not twice as productive as a team with a velocity of 20, and it may be less so. Ranking teams on velocity trains each team to raise its estimates, and the rise will look like improvement while delivery stays the same.

**4. Use a window, not a single sprint.** One sprint can be distorted by holidays, an incident, a team change, or one very large item. Look at the median and the range of the last five or six sprints, and annotate sprints with unusual events. A single low number is a prompt for a question, not a finding (see topic 1.6, Statistical literacy for service metrics).

### Anchor on the sprint goal

**5. Write the Sprint Goal as an outcome with a criterion you can check.** A goal such as "customers can reset their own password without calling the service desk" can be judged at the review. A goal such as "complete the sprint backlog" cannot add information. Record the criterion at planning, then record at the review whether it was met and what the team learned.

**6. Report sprint goal success as a rate with context, not a target.** A team that meets its goal in every sprint is probably choosing safe goals. A team that rarely meets it is probably over-committing or being interrupted. Look for a healthy middle and read the reasons recorded at each review. Treat the rate as a conversation starter, in line with the guidance on targets (see topic 1.2, Goodhart's law and the psychology of metrics).

**7. Link the goal to an outcome the business or customers care about.** Sprint goal success is more useful when it points at a customer or service result and not merely at output. If the goal is to cut repeat contacts about a service, record whether the repeat contact rate moved afterwards (see topic 1.3, Outcomes over output: choosing what to measure).

### Forecast honestly

**8. Compare forecast and actual, and look at the distribution.** For each sprint, record what the team forecast on day one and what it finished. Look at the spread across many sprints. Consistent small misses in one direction mean the forecast method is biased, for example the team is optimistic. This is the same pattern known as the [planning fallacy](https://en.wikipedia.org/wiki/Planning_fallacy): people underestimate the time work takes even when they know that similar work has run long before.

**9. Offer a probability, not a date.** When a stakeholder asks "when will this be done?", a single date implies certainty the team does not have. Use the history of throughput or velocity to give a range with a confidence level. A [Monte Carlo simulation](https://en.wikipedia.org/wiki/Monte_Carlo_method) can do this by replaying randomly sampled past sprints many times to show how often the work finished by each date. Teams without tooling can do a simpler version by hand using the best, median, and worst of recent sprints. Vacanti's *Actionable Agile Metrics for Productivity and Predictability* is a good practical source for throughput-based forecasting.

**10. Show the burn-up or burn-down in context.** A [burn down chart](https://en.wikipedia.org/wiki/Burn_down_chart) shows remaining work over time within a sprint or a release. A burn-up chart shows work done against total scope, which makes scope changes visible instead of hiding them in a moving baseline. Prefer the burn-up when scope changes, and annotate days when incidents or other interrupts took capacity (see topic 2.9, Operational work and unplanned work).

### Protect honesty and capacity

**11. Track mid-sprint scope change and its reasons.** Tag every addition or removal as planned change, incident, or request. If incident-driven additions are frequent, the sprint plan is not honest about the team's run commitments. Reserve capacity for interrupt work and show it in planning, rather than letting it quietly eat the forecast. The ratio of reserved to actual interrupt time is a better planning input than a blamed team.

**12. Pair velocity with quality and technical health.** Add escaped defects, reopen rate, or change fail rate beside velocity. If points rise while defects rise, the team is paying for speed with quality and with [technical debt](https://en.wikipedia.org/wiki/Technical_debt) (see topic 4.4, Change failure and rework, and topic 4.6, Technical debt and known errors). Ask, in the retrospective, whether the pace is sustainable and read the team's own view alongside the numbers (see topic 9.1, Team health and developer experience).

## Gaming vectors and guardrails

| Metric | How it gets gamed | Paired guardrail metric or practice |
| --- | --- | --- |
| Velocity | Inflating estimates so the same work scores more points; splitting items to claim partial credit; counting items as done before testing or release; padding with easy items near the sprint end | Sprint goal success rate and escaped defects beside it; compare throughput in items with points; review a sample of done items against the definition of done |
| Sprint goal success rate | Writing vague or trivially easy goals; redefining the goal at the review so it counts as met; changing the goal during the sprint | Record the goal and its criterion at planning; read the review notes; ask customers or stakeholders whether the outcome occurred |
| Forecast reliability | Forecasting low (sandbagging) so the team always finishes; forecasting only after learning the likely outcome; dropping hard items from the forecast mid-sprint | Track forecast against actual across many sprints and look for a consistent one-sided gap; compare with sprint goal success and stakeholder trust |
| Carryover rate | Closing an unfinished item and opening a new one for the remainder; shrinking items on paper to finish them in the sprint; marking items done and logging fixes as new defects | Count items linked as continuations; reopen rate and escaped defects; age of items from first start to done |
| Mid-sprint scope change | Not recording additions; recording incident work as part of the original plan; removing items quietly to protect the forecast | Compare the issue tracker change log with the sprint report; share of sprint time spent on unplanned work from the operations tool |
| Sprint throughput | Splitting items into trivial pieces to raise the count; closing items as won't do or merging them; moving work outside the tracked board | Review item size distribution; compare with velocity and sprint goal success; sample items for value delivered |

A healthy reading shows velocity and throughput within a stable range from sprint to sprint, with annotated dips for known events. Sprint goal success is somewhere between always and rarely, and the reasons for misses are recorded and acted on. Forecast reliability shows small misses in both directions rather than a consistent shortfall or consistent overshoot. Carryover is occasional and explained. Scope change is visible, tagged, and shrinking where a cause has been fixed. Quality measures hold steady while the speed measures move.

## Trade-offs: pros and cons

| Approach | Strength | Weakness |
| --- | --- | --- |
| Story points and velocity | Cheap once the team has a habit; absorbs differences in item size and complexity; useful in sprint planning conversations | Unit is private to the team; easy to inflate; says nothing about value; estimation effort can become its own overhead |
| Throughput (item count) | No estimating needed; harder to inflate by re-estimating; works for teams without sprints | Treats big and small items alike; needs reasonably consistent item sizes; the count can be gamed by splitting |
| Sprint goal success | Points at outcomes; easy to explain; links planning to review | Subjective; depends on how well the goal was written; can reward safe goals |
| Forecast reliability | Builds stakeholder trust; exposes optimism and sandbagging | Can penalize teams that rightly changed course; depends on a clear snapshot at sprint start |
| Carryover rate | Shows hidden overcommitment and slicing problems | Penalizes honest incomplete work; a low rate can come from shrinking items |
| Ranges and simulation | Honest about uncertainty; gives stakeholders probability | Needs history and some skill; can be mistaken for precision |

The prose answer is that no single sprint measure is enough. Velocity gives a team a working planning range, and sprint goal success keeps attention on the result. Forecast reliability checks that the range is believed, and scope change and quality measures show what the range cost. Teams with unstable sprints, many interrupts, or continuous flow work may find that cycle time and throughput forecasts serve them better than sprint measures. That is a legitimate choice, and the sprint can remain as a cadence for review and reflection without being a unit of measurement.

## Questions to discuss with your team

**1. What do we use our velocity for, and who else looks at it?**
Ask the team to list every use of the number, from planning to reports. For each audience, ask what they do with it and whether that use would survive the team inflating its estimates. The facilitator should look for any place where velocity appears in a target, a performance review, or a comparison with another team. Agree which uses to keep and which to retire.

**2. If someone asked us to double our velocity, what would we do, and what would happen to the product?**
This question surfaces the gaming vectors without accusation. Expect answers such as re-estimating, splitting items, skipping testing, and working longer hours. Write each answer on a board and ask which guardrail would catch it. The exercise often shows that the cheapest ways to raise the number are the most harmful ones.

**3. Looking at our last six sprints, how often did we meet the sprint goal, and why did we miss?**
Put the recorded goals and outcomes on a wall or screen. For each miss, ask whether the cause was over-commitment, an interrupt, an unclear goal, or a dependency on another team. The facilitator should look for repeated causes, because a repeated cause is a candidate for improvement work. Avoid asking who caused a miss.

**4. How much of each sprint goes to unplanned work, and is it in our plan?**
Pull the incident, request, and support data for recent sprints and compare it with the work in the sprint backlog. Discuss whether planning reserves any capacity for it. If the answer is none, the forecast is likely to miss by about the size of the interrupt load. Decide whether to reserve capacity, to move the interrupt work to a separate stream, or to change what is promised.

**5. Do our forecasts lean one way, and what would a range have told our stakeholders?**
Plot forecast against actual for as many sprints as you have. Look for a consistent gap rather than a single bad sprint. Then ask what the stakeholders would have done differently if they had been given a range with a confidence level in place of a single number. Agree on one change to how the team communicates its forecast.

**6. Which would serve us better, points or counting items, and what would we lose by changing?**
Compare a few sprints in both units. If both forecast equally well, the simpler unit may save the time spent estimating. Ask what conversations the estimating currently supports, such as surfacing unclear items, and whether those would still happen. Run the alternative for a few sprints before deciding, and keep the guardrails on whichever unit you use.

## Four perspectives

### Product and delivery teams

Delivery teams own these measures and use them in sprint planning and retrospectives. They should define done, write sprint goals as outcomes, keep a short history of sprints with annotations, and forecast in ranges. A team that sees its numbers drift should look at the work and the system before looking at effort. The team also decides when points no longer serve it and counting items or using flow measures would do better.

### Service and operations teams

Operations and support teams that share a backlog or an on-call rotation with delivery teams feel velocity most when interrupts are ignored. They should supply the interrupt data: incident, request, and support load per sprint. Sprint-style measures may fit poorly for a team whose work is mostly reactive, and flow measures such as cycle time and work item age may be a better fit (see topic 2.2, Lead time, cycle time, and flow efficiency). Where they do share a sprint, agree how incident work is shown, so it explains capacity instead of lowering a score (see topic 3.3, Incident response and resolution time).

### Leadership and governance

Leaders are the main source of pressure that corrupts velocity. They should ask for sprint goal success, outcomes, and forecast ranges rather than point totals, and should refuse to compare teams by velocity. A useful question in a review is "what did you learn from the last few sprints?" rather than "why is velocity down?". Governance bodies that need delivery assurance can ask for the guardrail view: goal success, forecast reliability, quality, and the share of time spent on unplanned work (see topic 11.3, Rolling out metrics without breeding fear).

### Customers and users

Customers rarely care about points. They care whether the thing they asked for arrives when they were told it would, and whether it works. Honest forecasts with a range and a confidence level serve them better than a confident date that slips. Sprint reviews, where they exist, are the right place for customers to judge the Sprint Goal, and their view should count more than the team's tally (see topic 6.1, Customer satisfaction metrics).

## In practice: an agile ITIL example

A mid-sized online retailer has a product team of seven that builds and runs the checkout and payment service. The team works in two-week sprints. All numbers in this example are illustrative.

For six sprints the team's velocity has been between 28 and 36 points, with a median of 32. The head of engineering is preparing a quarterly review and notices that another team in the same company reports a velocity near 60. A director asks why checkout is "slower". The head of engineering declines to compare the two, explaining that the two teams use different point scales, and asks the checkout team to share what they actually track.

The team puts three views on one page. First, sprint goal success: four of the last six goals were met, and the two misses are annotated. Second, forecast reliability: in five of six sprints the team finished between 80 and 110 percent of its day-one forecast, and in one it finished 55 percent. Third, unplanned work: the operations tool shows that sprint five contained two payment incidents and a holiday-traffic response that took roughly a third of the team's time.

The team sees that the 55 percent sprint and one missed goal are explained by the interrupt load, and that sprint planning never reserved capacity for it. Their decision is to reserve about 20 percent of each sprint's capacity as an interrupt allowance, to forecast from the median and lowest of the last six sprints, and to tell stakeholders "we expect to finish between 26 and 34 points, with the most likely near 30". They also agree to record the reason for each missed goal.

Two sprints later, the team notices a gaming risk of its own. Velocity has risen to 40 and 42 points, which pleases the director, but escaped defects in checkout have doubled over the same two sprints (illustrative), and several stories were re-estimated upward at refinement. The guardrail, escaped defects beside velocity, flags the pattern. In the retrospective the team admits it had started rounding estimates up to feel safe. They agree to estimate against a set of reference stories, to review done items against the definition of done, and to keep the velocity chart on the team's board instead of in the quarterly deck. The director receives goal success, the forecast range, and the quality trend instead, and agrees these are a better answer to "is checkout reliable?".

## Sector lens

**Startup.** Sprints are often short, goals shift quickly, and the team may be only four or five people. Velocity is useful for a few weeks and then drifts as the product changes. Keep the sprint goal and a simple count of items done, forecast in ranges, and avoid spending time on estimation ceremonies that the team does not find useful.

**Small business.** There may be one small team that builds, supports, and administers systems, so unplanned work dominates. Sprint measures can mislead when the sprint is mostly interrupts. Consider a simple weekly cadence, count items done, and show the owner the interrupt load so promises can be set realistically.

**Enterprise.** Many teams, shared dependencies, and pressure for comparable numbers make velocity especially prone to misuse. Publish a short standard set of sprint measures with written definitions, forbid cross-team velocity comparison in the measurement charter, and use goal success, flow measures, and outcome measures for roll-ups (see topic 1.4, Metrics governance and ownership). Where scaled frameworks exist, keep estimates and velocity at the team level.

**Government and public sector.** Fixed-price contracts, milestones, and audit trails can push suppliers to report velocity as proof of progress. Ask instead for working software demonstrated at the sprint review, sprint goal success, and forecast ranges tied to contractual outcomes. Make the definitions part of the contract so a supplier cannot change the scale of a point partway through, and keep records of sprint outcomes for audit.

## Business case: motivations, ROI, and TCO

The cost of these measures is small. Most of the data already lives in the issue tracker. The recurring costs are a few minutes per sprint to record the goal and the outcome, some time to annotate unusual sprints, and a short review of the forecast against the actual. Estimation sessions have their own cost, which a team may reduce by counting items instead of points. Tooling costs are usually limited to configuration of an existing tracker, or to a lightweight script or spreadsheet for ranges and simulation.

The return comes from better planning and fewer surprises. Stakeholders who receive ranges and confidence levels make better commitments, and the team is blamed less for misses it could not have avoided. Visible interrupt load supports a case for investing in problem management, automation, or more capacity, because it shows what unplanned work costs the plan. The measures also help a team spot over-commitment early. Describe the benefit through its pattern, such as fewer missed commitments, fewer last-minute scope changes, and agreement between the forecast and the delivered result. If a business case needs numbers, take the team's own baseline of forecast reliability and unplanned work share for a few sprints, then measure again after the changes (see topic 7.5, Service cost and unit economics).

The main risk to the return is misuse. If velocity becomes a target, the planning value disappears, and guardrails plus a rule that points stay private to the team are the cheapest insurance.

## Anti-patterns and pitfalls

- **Comparing teams by velocity.** Points are not a shared unit, so the comparison is meaningless and the pressure it creates inflates estimates. Compare each team with its own history and share outcomes instead.
- **Velocity targets or bonuses.** A target converts a planning aid into a goal, and the estimate moves to meet it. Remove the target and ask for sprint goal success and quality.
- **Individual velocity.** Points per person reward grabbing easy items and discourage helping others. Measure the team, and use the individual conversation to talk about the work.
- **Partial credit.** Counting half the points for half-finished items hides carryover and rewards starting. Count only done work and examine the carryover rate.
- **Ignoring interrupts.** A sprint plan that forgets incidents and requests sets the team up to miss. Reserve capacity, tag unplanned work, and show it in the sprint view.
- **Treating the sprint goal as a formality.** A goal that is just the list of backlog items adds no information. Write one objective with a checkable criterion and review it with stakeholders.

## Maturity model

| Dimension | 1 Initiate | 2 Develop | 3 Standardize | 4 Manage | 5 Orchestrate |
| --- | --- | --- | --- | --- | --- |
| Definitions and done | Each person decides what done means; points counted loosely | Some teams have a definition of done and count only finished items | One written definition of done and of each sprint measure, including clocks | Definitions reviewed and changes logged; samples checked against done | Definitions aligned with release and service practices and revised when they stop informing decisions |
| Forecasting | Single-number promises from memory | Velocity used by a few teams to plan | Ranges from a window of sprints, with annotations | Forecast against actual reviewed each sprint and bias corrected | Probabilistic forecasts shared with stakeholders and suppliers, tied to outcomes |
| Sprint goals and outcomes | Goals missing or a list of items | Goals written but judged informally | Goals state a checkable outcome and are judged at review | Goal success trended and linked to customer or service measures | Goals shaped with customers and aligned across dependent teams |
| Use and safety | Velocity used to rank or pressure | Teams see their own numbers | Points kept private to the team; no cross-team comparison | Guardrails shown beside speed measures and reviewed for gaming | Leaders, teams, and customers share an honest picture, including unplanned work |

## Checklist

- [ ] The team has a written definition of done and counts only items that meet it.
- [ ] Sprint goals are written as outcomes with a criterion checked at the review.
- [ ] Velocity is reported as a range over a window of recent sprints, with annotations.
- [ ] Velocity is never compared across teams, and no target or bonus depends on it.
- [ ] Forecast and actual are recorded for each sprint and reviewed for bias.
- [ ] Unplanned work is tagged, shown beside planned work, and reserved for in planning.
- [ ] A quality measure such as escaped defects or reopen rate sits beside velocity.
- [ ] Mid-sprint scope changes are recorded with a reason.
- [ ] The team has compared points with item counts and chosen the simpler unit that forecasts well.
- [ ] A gaming review of the sprint measures is on the calendar each quarter.

## AI prompts

**Forecast a range from sprint history.**

```text
I am the Scrum Master for [team name], a team of [number] people working on
[product or service]. Our sprints are [length] long. Here are our results for
the last [number] sprints, as points done, points forecast, and a note on any
unusual event: [paste data]. Describe the spread of the data, suggest how to
state a forecast for the next sprint as a range, and explain the method in
plain words so I can reproduce it by hand. Do not invent benchmark values or
compare us with other teams. List your assumptions and what extra data would
change the forecast.
```

**Review sprint goals for checkability.**

```text
Here are the Sprint Goals for [team name] over the last [number] sprints, with a
note on whether each was met: [paste goals and outcomes]. For each goal, say
whether it states an outcome that can be checked at the review, and suggest a
clearer wording where it does not. Look for patterns such as goals that restate
the backlog or goals that are always met. Do not judge individuals and do not
invent results. List your assumptions and any information you could not judge
from the text.
```

**Run a gaming review on sprint measures.**

```text
Our team reports these sprint measures: [list, for example velocity, sprint goal
success rate, carryover rate]. They are used by [audience] to [decision]. Our
data comes from [tool]. List realistic ways each measure could be made to look
better without improving delivery for users, and propose a guardrail measure or
practice for each. For each guardrail, name how it could be gamed. Do not invent
benchmark values. List your assumptions and what you could not determine.
```

## AI skills

- [Agile ITIL Metrics skill](../../../../skills/agile-itil-metrics-skill/SKILL.md): use to find the paired guardrail and related topics for any sprint measure you are about to report.
- [Agile ITIL Metrics maintainer skill](../../../../skills/agile-itil-metrics-maintainer-skill/SKILL.md): use to check that a revised version of this topic keeps its gaming vectors, guardrails, and cross-references intact.

## Key takeaways

- Velocity is a planning aid for one team, expressed as a range over recent sprints, and never a score or a basis for comparing teams.
- Sprint goal success keeps attention on outcomes, and it needs a goal written with a criterion that can be checked at the review.
- Forecast reliability tests whether the team's promises can be trusted, and probability ranges serve stakeholders better than single dates.
- Unplanned work belongs on the same view as planned work, or the sprint measures will blame the team for the system.
- Every speed measure needs a quality guardrail, and points are private to the team that owns them.
- Counting items is a simple alternative to points, and the choice between them should be tested with the team's own data.

## References and further reading

1. Schwaber, K., and Sutherland, J., *The Scrum Guide*, November 2020, https://scrumguides.org/scrum-guide.html.
2. Vacanti, D., *Actionable Agile Metrics for Productivity and Predictability*, ActionableAgile Press, 2015.
3. Cohn, M., *Agile Estimating and Planning*, Prentice Hall, 2005.
4. Beck, K., *Extreme Programming Explained: Embrace Change*, Addison-Wesley, 1999.
5. Forsgren, N., Humble, J., and Kim, G., *Accelerate: The Science of Lean Software and DevOps*, IT Revolution, 2018.
6. Forsgren, N., Storey, M.-A., Maddila, C., Zimmermann, T., Houck, B., and Butler, J., "The SPACE of Developer Productivity," *ACM Queue*, 19(1), 2021.
7. Goodhart, C. A. E., "Problems of Monetary Management: The U.K. Experience," in *Papers in Monetary Economics*, Reserve Bank of Australia, 1975.
8. Wikipedia, [Scrum (software development)](https://en.wikipedia.org/wiki/Scrum_(software_development)).
9. Wikipedia, [Sprint (software development)](https://en.wikipedia.org/wiki/Sprint_(software_development)).
10. Wikipedia, [Velocity (software development)](https://en.wikipedia.org/wiki/Velocity_(software_development)).
11. Wikipedia, [Story point](https://en.wikipedia.org/wiki/Story_point).
12. Wikipedia, [Planning poker](https://en.wikipedia.org/wiki/Planning_poker).
13. Wikipedia, [ITIL](https://en.wikipedia.org/wiki/ITIL).
14. Wikipedia, [Planning fallacy](https://en.wikipedia.org/wiki/Planning_fallacy).
15. Wikipedia, [Monte Carlo method](https://en.wikipedia.org/wiki/Monte_Carlo_method).
16. Wikipedia, [Burn down chart](https://en.wikipedia.org/wiki/Burn_down_chart).
17. Wikipedia, [Technical debt](https://en.wikipedia.org/wiki/Technical_debt).
