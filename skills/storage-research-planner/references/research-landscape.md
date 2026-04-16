# Research Landscape

Use this file when you need a fast orientation map for storage, databases, and distributed systems.
The point is not completeness. The point is to avoid designing or writing in a vacuum.

## Representative Industrial And Open-Source Systems

### Single-Node Storage Engines

- RocksDB: industrial LSM KV engine; compaction, WAL, block cache, iterators, snapshots, rate limiting, ingestion.
- LevelDB: smaller LSM baseline; useful for understanding simpler tradeoffs before RocksDB complexity.
- Pebble: CockroachDB's Go LSM engine; good reference for modern engine structure and test discipline.
- WiredTiger: B-tree plus LSM history inside MongoDB; useful for cache, reconciliation, and checkpoint ideas.
- Badger: value-log separated KV in Go; useful for vlog and GC tradeoffs.

### OLTP Databases

- PostgreSQL: canonical MVCC row-store with WAL, checkpoints, vacuum, buffer manager, planner/executor split.
- MySQL/InnoDB: industrial transactional engine with redo/undo, clustered indexes, purge, replication ecosystem.
- SQLite: single-file transactional database; useful when the topic is durability protocol, file layout, or embeddability.

### OLAP Databases

- DuckDB: in-process OLAP engine; vectorized execution, columnar storage, aggressive engineering clarity.
- ClickHouse: industrial OLAP system; MergeTree family, replication, ingestion, query serving.
- StarRocks: MPP analytical database with modern execution and lakehouse-facing features.

### Distributed Databases And KV Systems

- TiDB/TiKV: separated SQL/control/storage stack; Percolator-style transactions, Raft, PD, coprocessor path.
- CockroachDB: SQL on replicated KV; closed timestamp, Pebble, range-based metadata and leaseholder model.
- FoundationDB: ordered KV with strict layering and coordinator/controller split worth studying carefully.
- YugabyteDB: distributed SQL with DocDB/Raft foundations and PostgreSQL integration.
- Spanner: externally-consistent distributed database; TrueTime-centered design is a recurring reference point.
- HBase/Bigtable lineage: tablet-based serving, log-structured storage, background compaction, operational scale.

### Distributed Protocol And Coordination References

- Raft: understand leader-based replicated state machines and operational simplicity claims.
- Paxos / Multi-Paxos: baseline for consensus-family comparisons.
- Viewstamped Replication: useful for primary-backup and reconfiguration lineage.
- Zab: ZooKeeper-style atomic broadcast and coordination semantics.
- EPaxos: useful when comparing leaderless or dependency-aware replication.
- 2PC / Percolator / transaction timestamp oracles: relevant for distributed transactions and control-plane singleton duties.
- Delos and related metadata-root or log-root ideas: useful when the topic is rooted metadata or rebuildable control planes.

## How To Use The System Map

Use exemplars as comparison anchors, not as authority by name.
Compare by axis:
- storage structure
- authoritative metadata placement
- recovery contract
- control-plane truth boundary
- transaction model
- compaction or maintenance model
- operator-facing degraded mode

## Top Conferences By Subfield

### Databases And Data Management

- SIGMOD
- VLDB
- CIDR
- ICDE
- PODS

### Systems And Storage

- SOSP
- OSDI
- NSDI
- EuroSys
- FAST
- USENIX ATC

### Distributed Algorithms And Protocols

- PODC
- DISC
- SOSP and OSDI for systemized protocol work
- NSDI for networked and operational distributed-systems work

## Top Journals

- VLDB Journal
- ACM TODS
- IEEE TKDE
- ACM TOCS
- IEEE TPDS
- Journal of Parallel and Distributed Computing

## Venue Selection Heuristic

- If the main contribution is query processing, indexing, or DB architecture: start with SIGMOD, VLDB, CIDR, ICDE.
- If the main contribution is system boundary, recovery, distributed control, storage internals, or operational semantics: start with SOSP, OSDI, NSDI, EuroSys, FAST, ATC.
- If the main contribution is distributed protocol theory or formal boundary reasoning: check PODC and DISC in addition to systems venues.

Do not force a systems-heavy storage paper into a database-only framing, and do not force a query-engine paper into a generic distributed-systems framing.
