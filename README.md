# Storage Research Skills

Codex skills for storage, databases, and distributed-systems research.

This repository packages a small workflow-oriented skill set for:
- scouting hotspots from top venues and systems signals
- mining candidate research ideas from those hotspots
- triaging research ideas
- surveying papers and systems
- planning claims, invariants, and milestones
- implementing storage-engine internals carefully
- reviewing distributed-systems safety boundaries
- designing benchmarks and fault studies
- drafting systems papers

## Included Skills

- `storage-research-workflow`
  End-to-end idea discovery and triage: hotspot scouting, idea mining, real problem, prior art, feasibility, novelty, venue band, go/pivot/kill.
- `storage-research-planner`
  Turn an idea into claims, invariants, experiments, and milestones.
- `storage-literature-synthesizer`
  Read papers and systems as design constraints instead of generic summaries.
- `storage-engine-coder`
  Implement and refactor LSM/WAL/MVCC/recovery paths with correctness-first discipline.
- `distributed-storage-safety-review`
  Review control-plane, replication, durability, and recovery boundaries.
- `storage-benchmark-lab`
  Design credible benchmarks, fault injection, and evidence.
- `storage-systems-paper-writer`
  Write workshop/conference papers and design notes with bounded claims.

## Layout

```text
skills/
  distributed-storage-safety-review/
  storage-benchmark-lab/
  storage-engine-coder/
  storage-literature-synthesizer/
  storage-research-planner/
  storage-research-workflow/
  storage-systems-paper-writer/
```

Each skill follows the Codex skill layout:
- `SKILL.md`
- `agents/openai.yaml`
- optional `references/`

## Current Focus

The included references emphasize:
- single-node storage engines such as RocksDB, Pebble, WiredTiger, Badger
- OLTP systems such as PostgreSQL and InnoDB
- OLAP systems such as DuckDB and ClickHouse
- distributed systems such as TiDB/TiKV, CockroachDB, FoundationDB, YugabyteDB, Spanner
- protocol families such as Raft, Paxos, Viewstamped Replication, Zab, EPaxos, Percolator
- top venues across databases, systems, storage, and distributed protocols
- recent venue signals for hotspot scouting
- strict anti-hype idea review via a built-in fantasy detector

## Usage

Install or copy the desired skill folders into your local Codex skills directory.

Typical entrypoints:
- `Use $storage-research-workflow to evaluate this idea: ...`
- `Use $storage-research-planner to turn this topic into a claim and experiment plan.`
- `Use $storage-literature-synthesizer to position this design against prior work.`

## Status

This repository currently tracks a practical research workflow rather than a polished public release.
The skills are optimized for active systems research on storage and distributed-systems topics.
