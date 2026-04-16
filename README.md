# Storage Research Skills

Codex skills for storage, database, distributed-systems, distributed-file-system, and object-storage research.

## Why This Repo Exists

This repository is a single-theme research toolkit, not a generic skill marketplace.
It exists to make storage and systems research more disciplined by standardizing:
- topic discovery from real pressure rather than trend chasing
- idea triage before implementation
- prior-art and system-landscape review
- correctness-first implementation and benchmarking
- paper framing with bounded claims

## What You Get

The repository packages a compact research workflow for:
- scouting hotspot and pressure signals
- mining and triaging candidate ideas
- planning claim scope, invariants, and milestones
- reading papers as reusable system constraints
- reviewing safety boundaries across engines, databases, file systems, and object stores
- designing credible benchmark and fault evidence
- writing workshop and conference papers without inflating novelty

## Research Workflow

The intended flow is:
1. discover topic pressure with `storage-research-workflow`
2. normalize and triage the idea with intake, scorecard, and strict loop validation
3. deepen prior-art and system comparison with `storage-literature-synthesizer`
4. plan claims, invariants, experiments, and milestones with `storage-research-planner`
5. implement or refactor narrow system paths with `storage-engine-coder`
6. review correctness and lifecycle boundaries with `distributed-storage-safety-review`
7. produce benchmark and failure evidence with `storage-benchmark-lab`
8. write the design note or paper with `storage-systems-paper-writer`

## Included Skills

### Discovery

- `storage-research-workflow`
  End-to-end topic discovery and triage: hotspot scouting, idea mining, real-problem checks, prior art, feasibility, novelty, venue band, and go/pivot/kill.

### Analysis

- `storage-literature-synthesizer`
  Read papers and systems as design constraints, overlap surfaces, and related-work framing.
- `distributed-storage-safety-review`
  Review authority, durability, visibility, repair, rebalance, and degraded-mode boundaries across system classes.

### Building

- `storage-research-planner`
  Turn an idea into claims, invariants, experiments, and milestones.
- `storage-engine-coder`
  Implement and refactor storage-engine and database internals with correctness-first discipline.
- `storage-benchmark-lab`
  Design benchmark, profiling, recovery, and fault-injection evidence.

### Writing

- `storage-systems-paper-writer`
  Write workshop and conference papers, design notes, and rebuttals with bounded claims.

## Recommended Entry Points

Typical prompts:
- `Use $storage-research-workflow to evaluate this idea: ...`
- `Use $storage-research-workflow to scout 3 candidate topics in distributed storage.`
- `Use $storage-research-planner to turn this topic into a claim and experiment plan.`
- `Use $storage-literature-synthesizer to position this design against prior work.`
- `Use $distributed-storage-safety-review to audit this control-plane or metadata design.`

## Repository Layout

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

Each skill follows the same compact layout:
- `SKILL.md` for the workflow and trigger description
- `agents/openai.yaml` for UI metadata
- `references/` for load-on-demand detail

## Design Principles

- `one skill, one job`
  Each skill owns one stable responsibility. System-class variation lives in references, not in a god-skill.
- `workflow first`
  Skills are grouped by research lifecycle, not by product category.
- `references over bloated SKILL.md`
  Keep `SKILL.md` lean and move detail into load-on-demand references.
- `systems-first, evidence-first`
  Prefer explicit boundaries, falsifiable claims, and negative-path evidence over broad hype.
- `strict loop validation before build`
  Topic triage should aggressively test problem reality, overlap, feasibility, and evidence burden before implementation starts.

## Scope

The included references currently emphasize:
- single-node storage engines such as RocksDB, Pebble, WiredTiger, Badger
- OLTP systems such as PostgreSQL, MySQL/InnoDB, SQLite
- OLAP systems such as DuckDB, ClickHouse, StarRocks
- distributed databases and KV systems such as TiDB/TiKV, CockroachDB, FoundationDB, YugabyteDB, Spanner
- distributed file systems such as HDFS, CephFS, Lustre, JuiceFS, SeaweedFS
- object stores such as S3, MinIO, Ceph RGW, Swift
- protocol families such as Raft, Paxos, Viewstamped Replication, Zab, EPaxos, Percolator
- top conferences and journals across databases, systems, storage, and distributed protocols

## Install / Sync

Codex loads local skills from `~/.codex/skills` by default.
You can install the whole toolkit or only the skill folders you actually want.

### Install The Whole Toolkit

```bash
git clone https://github.com/feichai0017/storage-research-skills.git
cd storage-research-skills
mkdir -p ~/.codex/skills
rsync -a skills/ ~/.codex/skills/
```

### Install One Skill Only

```bash
git clone https://github.com/feichai0017/storage-research-skills.git
cd storage-research-skills
mkdir -p ~/.codex/skills
rsync -a skills/storage-research-workflow/ ~/.codex/skills/storage-research-workflow/
```

### Update Local Skills

```bash
cd storage-research-skills
git pull
rsync -a skills/ ~/.codex/skills/
```

After syncing, start a new Codex session if the skill list does not refresh automatically.

## Usage

Call a skill by name in your prompt.
Typical examples:

```text
Use $storage-research-workflow to evaluate this idea: ...
Use $storage-research-workflow to scout 3 candidate topics in distributed storage.
Use $storage-literature-synthesizer to position this design against prior work.
Use $distributed-storage-safety-review to audit this metadata or control-plane design.
Use $storage-benchmark-lab to design an evaluation plan for this claim.
Use $storage-systems-paper-writer to turn this prototype into a workshop paper outline.
```

Recommended starting points:
- use `storage-research-workflow` when you are still finding or filtering topics
- use `storage-literature-synthesizer` when you already have a topic and need prior-art clarity
- use `distributed-storage-safety-review` when the design touches authority, durability, visibility, or repair semantics
- use `storage-benchmark-lab` when you are about to make performance or recovery claims

## Status

This repository tracks an actively used research workflow rather than a polished marketplace release.
The current focus is practical systems research on storage and distributed-systems topics.
