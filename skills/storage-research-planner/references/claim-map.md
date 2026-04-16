# Claim Map

Use this template when scoping a storage or distributed-systems project.

## Problem

- What workload or failure mode matters?
- Which existing systems or designs are the comparison class?
- Why is the current situation unsatisfactory?

## System Boundary

- Authoritative state:
- Derived/service state:
- Local persistent state:
- Replicated persistent state:
- Failure model:
- Explicit non-goals:

## Claim Budget

Separate claims by type:

- Guaranteed property:
- Measured effect:
- Design hypothesis:
- Non-claim:

Good examples:
- "Startup fails on missing SST rather than silently repairing manifest state."
- "Coordinator rebuild resumes allocation from rooted lower bounds without service-local recovery state."
- "Page-local delta fold keeps dirty-page repair local rather than invalidating the whole parent."

Bad examples:
- "The design is more production-ready."
- "The protocol is better engineered."
- "This should be faster and cleaner."

## Evidence Plan

For each claim, record:
- proof surface
- test or benchmark surface
- expected counterexample
- cheapest artifact that would falsify the claim

## Build Order

Use this order unless the project has a stronger reason:
1. boundary cleanup
2. correctness and failure semantics
3. observability
4. evaluation
5. writing
