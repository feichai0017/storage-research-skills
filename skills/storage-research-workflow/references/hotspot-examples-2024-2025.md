# Hotspot Examples (2024-2025)

This file records example hotspots from recent public venue signals.
These are examples for scouting, not a closed list.

## Recurring Hotspot Families

### LLM Serving Meets Storage And Caching

Signals:
- OSDI 2024 includes work on dynamic KV cache management for LLM inference.
- FAST 2025 includes prefix KV storage and multi-tier KV management work.

Underlying pressure:
- transient state is now a storage hierarchy problem, not just a model problem
- prefix reuse, KV placement, eviction, and I/O-aware serving are becoming storage topics

### AI-Integrated Data Systems

Signals:
- SIGMOD 2025 includes LLM-based DB tuning and multiple AI-integrated data-system papers.
- VLDB 2025 publicly highlighted AI-integrated systems in its 2025 research news.

Underlying pressure:
- systems are moving from "use AI as a demo" to "expose a real systems contract around AI-assisted optimization or query execution"

### Hardware-Aware Indexing And GPU/PM Data Structures

Signals:
- VLDB 2025 highlights hardware-aware indexing.
- FAST 2025 includes GPU/persistent-memory and GPU-facing storage/index work.

Underlying pressure:
- index and storage structure design is again being constrained by device asymmetry, GPU access, and heterogeneous memory tiers

### Distributed Storage / Caching / Query Processing As Core NSDI Scope

Signals:
- NSDI 2025 CFP explicitly lists distributed storage, caching, and query processing systems.
- NSDI also lists networked systems for ML and testing/verification applied to networked systems.

Underlying pressure:
- distributed storage papers can increasingly win by combining strong systems semantics with practical evaluation, not only by building larger clusters

## How To Use These Examples

Do not copy the topic label.
Ask:
- what exact systems pressure is stable behind this theme?
- what narrow claim could survive after the hype cools down?
