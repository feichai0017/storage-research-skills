---
name: "storage-systems-paper-writer"
description: "Write storage, database, and distributed-systems papers, design notes, evaluation narratives, and rebuttals from real implementation and evidence. Use when turning a system or prototype into a workshop or conference paper while keeping claims bounded to what the artifact and experiments actually support."
---

# Storage Systems Paper Writer

## Overview

Use this skill to write evidence-bounded systems papers.
The writing should clarify the system boundary and supported claim, not inflate novelty.

## Workflow

1. State the paper type and strongest claim.
2. Build the outline around that claim.
3. Bind each section to specific evidence.
4. Write the system and evaluation sections before polishing the introduction.
5. Keep non-claims explicit.
6. Use related work to sharpen the boundary, not to spray citations.

## Default Paper Structure

Default sections:
1. problem and why the current boundary is bad
2. core observation
3. system model and boundary
4. design and protocol
5. implementation status
6. evaluation
7. limitations and non-claims
8. related work

Use `references/section-contracts.md` for section-by-section contracts.

## Writing Rules

- Do not claim a new consensus protocol unless you actually changed consensus.
- Do not package engineering cleanup as novelty.
- Do not claim generality beyond the tested boundary.
- Do not promise production readiness unless the operational evidence exists.

## Evidence Binding

Every major paragraph should answer one of:
- what exact problem exists
- what boundary changed
- what mechanism enforces the property
- what evidence supports the claim
- what remains outside the claim

## Output Modes

Use this skill for:
- paper outline
- abstract and introduction
- design section rewrite
- evaluation narrative
- related-work positioning
- rebuttal drafting
- long-form design note that may later become a paper

## Reference Loading

Load only what you need:
- `references/section-contracts.md` for paper-section writing contracts
- `references/venue-targeting.md` for top venue fit and framing differences across databases, systems, and protocol work
