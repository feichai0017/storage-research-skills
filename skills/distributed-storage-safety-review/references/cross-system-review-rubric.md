# Cross-System Review Rubric

Use this rubric when the review must generalize across system classes instead of staying inside a KV-store mental model.

Score or discuss each area explicitly.

## 1. Authority Boundary

Ask:
- What is authoritative for metadata, placement, membership, and visibility?
- Are there duplicated truths across config, catalog, cache, manifest, or repair state?
- Can background services or local shortcuts mutate authority outside the main path?

System-specific focus:
- single-node engines: manifest, catalog, page/extent map, checkpoint
- distributed DB/KV: range metadata, leases, epochs, transaction timestamps
- distributed file systems: namespace truth, inode/dentry ownership, block-placement authority
- object stores: bucket/object metadata, multipart state, object-version visibility, placement map

## 2. Durability Boundary

Ask:
- What exact write protocol makes state durable?
- Are rename, checkpoint, flush, WAL, manifest, or log-commit steps explicit?
- After sync failure, does the system poison itself or keep serving incorrectly?

System-specific focus:
- engines: WAL/checkpoint/manifest ordering
- distributed systems: replicated commit versus local durable staging
- file/object systems: metadata versus chunk/object durability mismatch

## 3. Namespace / Object Visibility Semantics

Ask:
- When does a name, object, version, or snapshot become visible?
- Are negative lookups, stale views, and degraded reads explicit?
- Can client-visible state observe mixed epochs after failover, rename, repair, or multipart completion?

System-specific focus:
- databases: schema/catalog visibility and transaction-visible metadata
- file systems: rename, directory listing, snapshot, lease/cache coherence
- object stores: multipart completion, versioned visibility, lifecycle/tiering semantics

## 4. Repair / GC / Rebalance Safety

Ask:
- Can repair, scrub, compaction, GC, healing, or rebalance race the authoritative state?
- Are maintenance jobs local, global, or incremental in a justified way?
- Can background work silently repair away corruption or create a new inconsistency window?

System-specific focus:
- engines: compaction, GC, vacuum, checkpoint cleanup
- distributed DB/KV: snapshot install, split/merge cleanup, re-replication
- file systems: scrub, rebalance, block healing, orphan cleanup
- object stores: healing, tiering, lifecycle deletes, multipart GC

## 5. Degraded-Mode And Operator Safety

Ask:
- What happens when quorum, metadata service, or placement control is impaired?
- Does the system reject, degrade explicitly, or guess?
- Can operators tell whether the system is stale, unavailable, uncovered, or actively unsafe?

System-specific focus:
- distributed DB/KV: stale route cache, lease ambiguity, degraded control plane
- file systems: namespace service failover, client-cache invalidation, block-location staleness
- object stores: stale object listing, partial region outage, healing backlog, consistency mode

## Output Rule

For each of the 5 areas, report:
- current boundary
- main risk
- failure mode
- simplest hardening direction
