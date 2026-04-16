---
name: storage-literature-synthesizer
description: Read storage, database, and distributed-systems papers and turn them into reusable design constraints, assumptions, mechanisms, positioning, and hotspot maps. Use when surveying a topic, discovering emerging directions, extracting implementation ideas, comparing systems, or building related-work and novelty framing.
---

# Storage Literature Synthesizer

## Overview

Use this skill to read papers like an implementer and a paper writer at the same time.
The output should be a design map, not a generic summary.

## Workflow

1. Read with a concrete question.
2. Extract boundary, mechanism, and claim separately.
3. Distinguish what is authoritative from what is optimization or packaging.
4. Build a comparison table against adjacent systems.
5. Translate the paper into reusable research pressure for your own work.
6. Cluster repeated papers into hotspot families when the user asks for topic discovery.

## Reading Questions

Read papers by asking:
- What exact problem does this system narrow?
- What must be true for the design to work?
- Where is the truth boundary?
- Which parts are protocol, and which are engineering?
- What does the evaluation really prove?
- What would fail if one assumption changed?

## Extraction Rules

For every paper, extract these fields:
- system goal
- state and ownership model
- core mechanism
- safety condition
- steady-state cost
- failure or degraded-mode story
- explicit non-goals
- strongest supported claim
- weakest part of the evidence

Use `references/paper-digest-template.md` for the exact template.

## Positioning Rules

Do not position by adjectives such as "simpler", "better", or "more practical".
Position by axis:
- truth placement
- recovery authority
- compaction or indexing contract
- read/write amplification tradeoff
- metadata/control-plane split
- answerability or freshness semantics

## Output Modes

Common outputs:
- one-paper design digest
- side-by-side comparison table
- design lineage from older systems to newer ones
- related-work section material
- novelty-boundary note for your own project
- hotspot map from recent venue signals

## Failure Modes To Avoid

- summarizing implementation detail without isolating the protocol
- repeating the abstract instead of identifying the real constraint
- claiming novelty where the paper only changes packaging
- copying benchmark numbers without checking the compared path or workload

## Reference Loading

Load only what you need:
- `references/paper-digest-template.md` for structured paper digestion
- `references/system-landscape.md` for industrial/open-source reference systems worth comparing against
- `references/venue-map.md` for top conferences and journals by subfield
- `references/hotspot-reading.md` for turning recent accepted papers and CFPs into hotspot maps
