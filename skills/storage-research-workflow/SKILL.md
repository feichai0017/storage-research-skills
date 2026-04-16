---
name: storage-research-workflow
description: Run an end-to-end workflow for storage, database, and distributed-systems research ideas: scout hotspots, mine directions, test whether the problem is real, search prior art, judge feasibility, assess novelty, estimate likely venue level, and decide whether to invest in implementation or writing. Use when actively looking for topics, triaging a new idea, or deciding whether an existing prototype is publishable.
---

# Storage Research Workflow

## Overview

Use this skill as the top-level funnel for systems research.
It is meant to stop weak ideas early and concentrate effort on problems with real pressure, a believable mechanism, and a plausible paper target.

## What This Skill Produces

The output should include:
- a hotspot or pressure map when the user has no idea yet
- a one-paragraph problem framing
- a five-dimension scorecard
- a prior-art and overlap judgment
- a feasibility judgment
- a novelty judgment
- a likely venue band
- a go / pivot / kill recommendation
- a concrete next step

## Core Rule

Do not ask "is this cool?"
Ask, in order:
1. Why is this topic hot now?
2. Is there a real systems pressure hiding under the hype?
3. Has this already been done closely enough?
4. Can we actually build and evaluate it?
5. Is the contribution strong enough for a target venue?

## Workflow Funnel

1. Scout hotspots and pressure points.
2. Mine concrete idea candidates from those hotspots.
3. Normalize the candidate into an intake.
4. Validate that the problem is real.
5. Search industrial systems and academic prior art.
6. Frame the precise contribution candidate.
7. Run the fantasy detector.
8. Judge build feasibility.
9. Judge evaluation feasibility.
10. Judge novelty and contribution depth.
11. Estimate venue band.
12. Decide go, pivot, or kill.

## Step 1: Scout Hotspots And Pressure Points

When the user does not already have an idea, start from public research signals:
- recent accepted papers in top venues
- recent workshop themes
- conference CFP topic lists
- keynote themes
- repeated engineering pain in serious open-source systems

Do not confuse a hot keyword with a good problem.
The goal is to locate repeated pressure, not to imitate titles.

Use `references/hotspot-scouting.md` for the scouting workflow.

## Step 2: Mine Candidate Ideas

Turn hotspot observations into candidate problems by asking:
- what recurring bottleneck or semantic gap appears behind this trend?
- which assumptions are currently hand-waved?
- where are systems falling back to hidden heuristics, silent repair, or unclear service semantics?
- what narrow slice could be built and falsified quickly?

Use `references/idea-mining.md` for the mining patterns.

## Step 3: Choose The Topic Source

Valid sources:
- recurring engineering pain in a real system
- mismatch between known systems and a new workload
- clear gap or weak assumption in prior papers
- strong negative result that reveals a missing boundary
- operational pain such as degraded control plane, recovery, or maintenance cost

Weak sources:
- "this sounds elegant"
- "I can implement this quickly"
- "nobody seems to have named it exactly this way"

## Step 4: Validate The Problem Is Real

Check:
- who pays the cost today
- what failure, overhead, or operational pain exists
- whether the pain shows up in real systems or established literature
- whether the problem survives after obvious simplifications
- whether the problem is large enough to matter to a venue community

Use `references/workflow-funnel.md` for the full gate questions.

## Step 5: Search Prior Art

Search three layers:
- industrial systems and open-source exemplars
- top conference and journal papers
- adjacent designs that solve part of the problem under different assumptions

When searching, use primary sources where possible:
- official docs and code for systems
- original papers for mechanisms
- benchmark methods from the source papers, not second-hand summaries

The question is not only "has anyone done this?"
The question is "has anyone already occupied this claim boundary closely enough that our version would look incremental?"

## Step 6: Frame The Contribution Candidate

Force the idea into one of these shapes:
- new system boundary
- new safety or recovery property
- new control-plane or metadata organization
- new read/write/maintenance contract
- new evidence on a previously fuzzy systems problem
- useful negative result that kills a bad assumption

If the only answer is "a cleaner implementation", the idea is probably too weak.

## Step 7: Run The Fantasy Detector

Before spending time on implementation, try to kill the idea aggressively.
This is the "玄幻检测" step.

Ask:
- is the problem real, or only fashionable?
- is the mechanism actually different, or just new vocabulary on an old pattern?
- are we relying on impossible scale, unavailable traces, or unfair baselines?
- would a skeptical reviewer say "this is just X with a new wrapper"?
- does the hoped-for claim exceed the artifact that can realistically be built?

Use `references/fantasy-detector.md`.

## Step 8: Judge Feasibility

Judge two things separately:
- build feasibility
- proof or evidence feasibility

An idea is weak if:
- it needs infrastructure you do not control
- it depends on impossible baselines
- it needs months of engineering before the first falsifiable result
- it cannot be evaluated against a believable competing design

## Step 9: Judge Novelty

Novelty is not a vibe. Score it by:
- claim overlap with prior papers
- mechanism overlap
- evidence overlap
- workload or failure model difference
- whether the main contribution is protocol, architecture, or only engineering hygiene

Use `references/novelty-rubric.md` when you need a stricter ladder.

## Step 10: Estimate Venue Band

Estimate the best plausible band, not the dream venue.

Typical bands:
- design note / workshop / preprint
- FAST / ATC / EuroSys / ICDE range
- NSDI / OSDI / SOSP / SIGMOD / VLDB range
- protocol venue such as PODC / DISC when proof burden dominates

Use `references/venue-band-rubric.md` for the actual bar.

## Step 11: Final Decision

Choose one:
- `GO`: real problem, manageable overlap, feasible build and eval, credible venue band
- `PIVOT`: real problem but current mechanism or framing is weak
- `KILL`: fake problem, saturated prior art, infeasible proof burden, or venue bar too far from likely evidence

## Output Format

Always return:
1. idea statement
2. hotspot or pressure source
3. five-dimension scorecard
4. real-problem verdict
5. prior-art verdict
6. feasibility verdict
7. novelty verdict
8. likely venue band
9. go / pivot / kill
10. next 2-3 concrete actions

## Scorecard Rule

Always score these five dimensions:
- problem reality
- prior-art risk
- feasibility
- novelty
- venue band

Use `references/scorecard.md` for the scoring scale and return format.

## Intake Rule

When the user provides a new idea, normalize it into the intake template before judging it.
Use `references/idea-intake-template.md` for the template.

When the user asks for topic discovery instead of scoring an existing idea:
1. scout hotspots
2. list candidate tensions
3. pick 3-5 candidate ideas
4. run the same scorecard and fantasy detector on each one

## Relationship To Other Skills

This is the orchestrator.
When a branch becomes concrete, use:
- `$storage-research-planner` for claim shaping and milestone planning
- `$storage-literature-synthesizer` for deeper paper digestion
- `$storage-benchmark-lab` for evaluation design
- `$storage-systems-paper-writer` for drafting

## Reference Loading

Load only what you need:
- `references/workflow-funnel.md` for the full end-to-end decision process
- `references/hotspot-scouting.md` for active topic discovery
- `references/idea-mining.md` for turning trends into idea candidates
- `references/fantasy-detector.md` for strict anti-hype feasibility checks
- `references/hotspot-examples-2024-2025.md` for recent example hotspots from public venue signals
- `references/scorecard.md` for the five-dimension quantitative output
- `references/idea-intake-template.md` for normalizing new ideas into a consistent intake form
- `references/novelty-rubric.md` for judging contribution depth
- `references/venue-band-rubric.md` for paper-level estimation
- `references/kill-signals.md` for early rejection patterns
