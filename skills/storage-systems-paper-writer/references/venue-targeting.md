# Venue Targeting

Use this file when a draft needs to be framed for a specific community.

## Database Venues

Primary venues:
- SIGMOD
- VLDB
- CIDR
- ICDE

Bias in framing:
- clearer data-management problem statement
- stronger baseline comparisons on query, indexing, or transaction axes
- sharper explanation of why the mechanism matters to DB workloads

## Systems And Storage Venues

Primary venues:
- SOSP
- OSDI
- NSDI
- EuroSys
- FAST
- USENIX ATC

Bias in framing:
- stronger system boundary argument
- more explicit failure and recovery semantics
- more emphasis on end-to-end behavior and operator-visible tradeoffs

## Protocol-Theory Venues

Primary venues:
- PODC
- DISC

Bias in framing:
- cleaner model assumptions
- more formal invariants and proof obligations
- less tolerance for fuzzy operational claims

## Journals

Useful top journals:
- VLDB Journal
- ACM TODS
- IEEE TKDE
- ACM TOCS
- IEEE TPDS

## Selection Rule

Pick the venue family that matches the hardest part of the contribution:
- query/index/transaction contribution: database venue
- recovery/control-plane/storage-boundary contribution: systems venue
- proof-heavy consensus or coordination contribution: protocol venue

Do not retarget only by changing the abstract vocabulary.
The evaluation and related-work sections must also move with the venue.
