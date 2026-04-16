---
name: distributed-storage-safety-review
description: Review storage, database, distributed-systems, distributed-file-system, and object-storage designs or code for correctness, durability, recovery, membership safety, metadata discipline, and lifecycle robustness. Use when auditing a PR, design doc, incident, test plan, or research roadmap involving replicated state, storage metadata, namespace service, control-plane logic, or distributed data movement.
---

# Distributed Storage Safety Review

## Overview

Use this skill to review distributed storage and database systems with a findings-first mindset.
The main job is to identify concrete failure modes and weak boundaries, not to summarize architecture politely.

## Review Stance

- Prefer one authority boundary over multiple loosely coupled truths.
- Treat cancellation, retry, restart, and failover as part of correctness.
- Assume hidden background repair will eventually become a production outage.
- Judge designs by takeover and recovery behavior, not by steady-state happy path.
- Adapt the checklist to the system class instead of forcing every repository into a KV-store shape.

## Workflow

1. Map the authoritative state and routing/control surfaces.
2. Identify the dominant state transition type for the system.
3. Inspect cancellation, timeout, retry, and queue overflow behavior.
4. Inspect recovery, replay, bootstrap, namespace repair, and restart semantics.
5. Inspect mutation authority and who is allowed to change authoritative metadata.
6. Report prioritized findings with concrete correction direction.

## Review Dimensions

Check:
- truth and authority placement
- durability and replay semantics
- failover and lease/fence transfer
- request context propagation
- split/merge/bootstrap/snapshot restart safety
- local mutation escape hatches
- shutdown admission and in-flight work control
- degraded-mode behavior when PD/coordinator/control plane is unavailable
- namespace and metadata consistency for file or object systems
- background repair, scrub, rebalance, or GC safety for long-running systems

## Output Rules

Findings come first.
For each finding, state:
- where it is
- what failure it permits
- why the current boundary is insufficient
- the simplest correction direction

Use `references/review-checklist.md` when you need the detailed prompts.

## What Not To Do

- do not praise by default
- do not confuse "works in tests" with a safe protocol
- do not accept duplicated truth sources without a hard reason
- do not treat recovery semantics as operational detail

## Reference Loading

Load only what you need:
- `references/review-checklist.md` for distributed-safety review prompts
