---
name: storage-research-planner
description: Plan and steer storage, database, and distributed-systems research from problem framing to claim scoping, invariants, experiments, and milestones. Use when starting a new topic, turning engineering pain into a research question, decomposing a large agenda, or deciding what to build and measure first.
---

# Storage Research Planner

## Overview

Use this skill to turn a broad storage or distributed-systems idea into a tight research program.
The goal is to leave with a bounded claim, a system boundary, an experiment plan, and a build order.

## Workflow

1. Define the system boundary.
2. State the property that matters.
3. Convert the property into a claim budget.
4. Pick the evidence required to support or reject the claim.
5. Sequence implementation work so correctness comes before speed.
6. Produce a concrete next-step plan.

## Step 1: Define The System Boundary

Write down:
- workload shape
- trust and failure model
- authoritative state
- service/view layers
- local versus replicated state
- admission and shutdown boundaries

If those nouns are fuzzy, the topic is not ready for optimization or paper framing.

## Step 2: State The Property

Prefer one primary property per work item:
- crash safety
- durability protocol correctness
- recovery strictness
- read/write path latency
- metadata scalability
- control-plane rebuildability
- snapshot/install cost
- listing/query answerability

Do not mix "faster", "cleaner", and "more correct" into one fuzzy goal.

## Step 3: Build A Claim Budget

Force every claim into one of these buckets:
- guaranteed property
- measured effect
- design hypothesis
- non-goal

Use `references/claim-map.md` when you need the exact format.

## Step 4: Pick Evidence Early

Match the claim to evidence:
- correctness claim: negative tests, crash tests, recovery tests, failpoints
- performance claim: benchmark with workload axes and baselines
- architecture claim: explicit state-machine or ownership boundary
- operator claim: degraded-mode and restart behavior

If you cannot say what evidence would falsify the claim, the claim is too soft.

## Step 5: Sequence The Work

Default order:
1. make boundaries explicit
2. land correctness and recovery semantics
3. add observability and fault surfaces
4. measure the stable design
5. write the note or paper

Do not lead with benchmarking if the invariants are still moving.

## Step 6: Expected Outputs

Produce some subset of:
- a one-paragraph problem statement
- a bounded claim list
- an invariant list
- an implementation plan
- an experiment matrix
- a milestone plan with "must prove" checkpoints

## Reference Loading

Load only what you need:
- `references/claim-map.md` for claim shaping and non-claims
- `references/research-landscape.md` for representative industrial systems and top venues by subfield
