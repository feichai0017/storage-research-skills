---
name: "storage-engine-coder"
description: "Implement or refactor single-node storage-engine and database internals such as LSM trees, B-trees, WAL, MVCC, iterators, compaction, checkpoints, snapshots, file formats, metadata indexes, and hot read/write paths. Use when writing low-level code or tests where invariants, durability, and lifecycle safety matter more than API polish."
---

# Storage Engine Coder

## Overview

Use this skill for narrow, correctness-first changes in storage internals.
The default stance is to make the smallest defensible change that preserves clear ownership and explicit failure semantics.

## Non-Negotiables

- Map the exact state transition before editing.
- Prefer explicit invariants over helper layers.
- Return errors instead of hiding recovery behind silent repair.
- Treat durability protocol failures as state-corrupting until proven otherwise.
- Do not mix semantic fixes and performance tuning unless the optimization is required for the fix.

## Workflow

1. Identify the truth boundary and the exact mutation path.
2. Write down the invariant being changed.
3. Inspect open, close, recovery, and error paths before touching the hot path.
4. Make the smallest implementation change.
5. Add targeted negative-path tests in the same change.
6. Benchmark only after correctness is stable.

## Coding Priorities

Priority order:
1. correctness and recovery
2. boundary and lifecycle clarity
3. observability
4. hot-path optimization

## What To Inspect

For engine work, inspect:
- ownership of buffers and borrowed memory
- manifest or metadata durability protocol
- fsync, rename, and parent-dir sync behavior
- iterator lifetime and visibility rules
- startup strictness on missing or corrupt state
- shutdown and admission gating
- interactions between WAL, memtable, compaction, snapshots, and value separation
- catalog, page, extent, or object-metadata consistency when the engine is not LSM-based

Use `references/implementation-checklist.md` when you need the detailed checklist.

## Test Rules

- Every correctness-sensitive change gets targeted tests in the same patch.
- Prefer one test per failure mode over one giant scenario test.
- Include negative paths: restart, partial write, missing file, stale metadata, iterator invalidation, cancellation, double close, poisoned state.
- If the change can only be justified by performance, produce a workload and baseline before claiming improvement.

## Output Expectations

When using this skill, report:
- invariant changed
- exact code path touched
- tests added or updated
- residual risk if any

## Reference Loading

Load only what you need:
- `references/implementation-checklist.md` for engine-side review and patch discipline
