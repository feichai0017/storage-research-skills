---
name: storage-benchmark-lab
description: Design and interpret trustworthy performance studies, failure injection, recovery tests, and profiling runs for storage, database, and distributed systems. Use when making latency or throughput claims, comparing baselines, validating optimizations, or proving a fix survives load and faults.
---

# Storage Benchmark Lab

## Overview

Use this skill to turn performance work into credible evidence instead of benchmark theater.
The benchmark is part of the claim boundary, not a decorative appendix.

## Workflow

1. Start from the claim.
2. Define workload axes and failure axes.
3. Lock down correctness gates before timing anything.
4. Choose honest baselines.
5. Separate steady-state, degraded, and recovery measurements.
6. Report caveats and unsupported interpretations.

## Benchmark Rules

- A microbenchmark must name the code path it isolates.
- A system benchmark must name the feature set it exercises.
- If correctness semantics differ, do not compare raw numbers without saying so.
- If a benchmark depends on warm state, say exactly what is warmed.

## Required Surfaces

For storage work, consider:
- point reads and scans
- write path with realistic batch and fsync modes
- recovery time
- compaction or GC interference
- snapshot/install or catch-up cost
- control-plane outage or stale-routing mode
- tail latency under mixed load

Use `references/evidence-rules.md` when you need the detailed checklist.

## Failure-Injection Rule

If the work touches correctness or durability, pair the benchmark with at least one fault or restart surface.
Fast but silently repairable is not an acceptable result.

## Reporting Rules

Always report:
- exact workload
- data shape
- fsync or durability mode
- hardware and runtime context
- baselines
- unsupported conclusions

## Reference Loading

Load only what you need:
- `references/evidence-rules.md` for performance and failure-study discipline
