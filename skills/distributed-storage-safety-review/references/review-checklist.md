# Distributed Safety Review Checklist

Use this checklist for:
- distributed KV stores
- distributed SQL databases
- metadata services
- distributed file systems
- object stores
- replicated control planes

Adapt the prompts to the system class instead of forcing a KV-centric review.

## Authority

- What is the single authoritative source for each kind of metadata?
- Are there parallel truths across config, local manifest, runtime cache, or coordinator service?

### File / Object Extension

- what is authoritative for namespace metadata?
- what is authoritative for object placement or chunk location?
- can background repair or garbage collection race the namespace truth?

## Mutation Discipline

- Can local code mutate replicated metadata without going through apply or consensus?
- Are admin paths narrower and more constrained than normal writes?

### Database Extension

- can schema, catalog, or transaction-visible state move through side channels?

### DFS / Object Extension

- can rebalancing, scrub, healing, or multipart completion mutate visible state outside the normal authority path?

## Recovery

- What happens on missing or corrupt local state?
- Does startup fail fast, repair silently, or diverge?
- Can a restarted node serve stale or unsafe state before catch-up completes?

### File / Object Extension

- what happens when data blocks exist but namespace metadata does not, or vice versa?
- what happens when index/manifests point to missing extents, chunks, or object parts?

## Control Plane

- What happens if the coordinator or PD is unavailable after startup?
- Is freshness explicit or hidden behind retries and stale caches?
- Are lease transfer and allocator lower bounds rooted in one authority?

### No-Central-Coordinator Extension

- what is the placement, membership, or namespace control surface?
- how are stale routing and stale ownership detected and exposed?

## Lifecycle

- Is shutdown gated explicitly?
- Do request contexts propagate end-to-end?
- What happens on queue overflow, deadline expiry, or transport drop?

## System-Class Prompts

### Single-Node Storage Engines

- Are WAL, manifest, checkpoint, and compaction boundaries explicit?
- Can restart silently discard durable metadata?
- Are iterators, snapshots, and GC visibility rules coherent?

### Distributed Databases / KV Stores

- Is replicated metadata mutated only through consensus or apply?
- Are split/merge/bootstrap/snapshot flows restart-safe?
- Are leases, epochs, timestamps, or fences tied to one authority?

### Distributed File Systems

- Is namespace truth separate from block placement and repair state?
- Can directory rename, snapshot, or lease recovery expose mixed epochs?
- Can data-repair workflows create namespace-visible corruption windows?

### Object Stores

- Is bucket/object versioning authoritative and explicit?
- Are multipart upload, lifecycle, compaction, or tiering transitions crash-safe?
- Can background healing or metadata rebuild change client-visible semantics unexpectedly?
