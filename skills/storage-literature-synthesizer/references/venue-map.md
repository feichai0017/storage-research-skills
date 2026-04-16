# Venue Map

Use this file when deciding where to search for papers or how to frame a draft.

## Top Conferences

### Database-Focused

- SIGMOD
- VLDB
- CIDR
- ICDE
- PODS

### Systems-Focused

- SOSP
- OSDI
- NSDI
- EuroSys
- FAST
- USENIX ATC

### Distributed Algorithms And Theory

- PODC
- DISC

## Top Journals

- VLDB Journal
- ACM TODS
- IEEE TKDE
- ACM TOCS
- IEEE TPDS

## Practical Search Heuristic

- For LSM, KV engines, WAL, compaction, snapshots, metadata services, and storage internals: search FAST, OSDI, SOSP, EuroSys, NSDI, SIGMOD, VLDB.
- For OLTP engines, indexing, transactions, recovery, and optimizer or storage-manager work: search SIGMOD, VLDB, ICDE, CIDR, TODS, TKDE.
- For OLAP engines, execution models, vectorization, column stores, and query processing: search SIGMOD, VLDB, CIDR, ICDE.
- For replicated metadata, consensus, leases, reconfiguration, and formal protocol boundaries: search PODC, DISC, OSDI, SOSP, NSDI.

## Writing Heuristic

Venue fit changes the framing:
- database venues usually expect sharper data-model, query, indexing, or transaction framing
- systems venues usually expect stronger boundary, failure, operational, and whole-system argument
- protocol venues usually expect tighter model assumptions and proof discipline
