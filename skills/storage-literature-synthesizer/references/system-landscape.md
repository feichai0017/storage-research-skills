# System Landscape

Use this as a seed list for paper search, comparison tables, and related-work framing.

## Single-Node Storage Engines

- RocksDB
- LevelDB
- Pebble
- WiredTiger
- Badger

Good for topics such as:
- LSM design
- compaction scheduling
- memtable and WAL design
- point-read and iterator engineering
- value separation and GC

## OLTP Databases

- PostgreSQL
- MySQL / InnoDB
- SQLite

Good for topics such as:
- MVCC
- WAL and checkpointing
- vacuum or garbage collection
- indexing and planner/executor boundaries
- crash recovery and durability semantics

## OLAP Databases

- DuckDB
- ClickHouse
- StarRocks

Good for topics such as:
- vectorized execution
- columnar layout
- compression and late materialization
- analytical concurrency control
- local versus distributed OLAP tradeoffs

## Distributed File Systems

- HDFS
- CephFS
- Lustre
- JuiceFS
- SeaweedFS

Good for topics such as:
- namespace service design
- metadata and chunk-placement separation
- rename and snapshot semantics
- lease recovery and client cache consistency
- data repair, rebalance, and scrub behavior

## Object Storage Systems

- Amazon S3 as the service model reference
- Ceph RGW
- MinIO
- SeaweedFS object layer
- OpenStack Swift

Good for topics such as:
- bucket/object metadata layout
- multipart upload and versioning semantics
- erasure coding, healing, and rebuild paths
- lifecycle/tiering and object visibility
- metadata versus data placement authority

## Distributed Databases And KV Stores

- TiDB / TiKV
- CockroachDB
- FoundationDB
- YugabyteDB
- Spanner
- Bigtable / HBase lineage

Good for topics such as:
- control-plane and metadata placement
- transaction protocols
- timestamp allocation
- range or tablet management
- split/merge and snapshot movement
- degraded control-plane behavior

## Distributed Protocol References

- Raft
- Paxos / Multi-Paxos
- Viewstamped Replication
- Zab
- EPaxos
- Percolator

Use these when the paper or project hinges on:
- leader election and term fencing
- reconfiguration
- distributed commit
- coordination ownership
- timestamp or allocator semantics

## Positioning Rule

Do not cite systems just because they are famous.
Choose comparison systems that share at least one hard axis with the target work:
- same authority boundary
- same storage structure
- same transaction model
- same maintenance path
- same failure or recovery concern
- same namespace or object-visibility semantics
