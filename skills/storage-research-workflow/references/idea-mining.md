# Idea Mining

Use this after hotspot scouting.

## Principle

A hotspot is not an idea.
Convert hotspots into ideas by finding a narrow, falsifiable systems tension.

## Mining Patterns

### Pattern 1: Contract Gap

Ask:
- where do existing systems rely on heuristics or hidden fallback?
- where is service behavior useful but not explicitly specified?

Good output:
- explicit freshness contract
- answerability contract
- strict degraded-mode contract
- stateless-client metadata serving contract

### Pattern 2: Authority Gap

Ask:
- where is truth split across too many layers?
- where does recovery need to stitch together state from multiple authorities?

Good output:
- rooted ownership transfer
- rebuildable control plane
- stricter startup or recovery semantics

### Pattern 3: Maintenance Gap

Ask:
- where is the steady-state path decent but rebuild/repair/compaction too heavy?
- where is background maintenance global when it should be local?

Good output:
- page-local maintenance
- incremental rebuild
- explicit maintenance certificate

### Pattern 4: Evaluation Gap

Ask:
- where are papers making assumptions no one has audited carefully?
- where do benchmark conventions hide a semantic mismatch?

Good output:
- benchmark artifact
- workload audit
- negative-result paper

## Candidate Compression

Compress every candidate into:
- pressure
- mechanism
- falsifiable claim

If you cannot do that in 3 lines, the candidate is still too vague.
