# Distributed Safety Review Checklist

## Authority

- What is the single authoritative source for each kind of metadata?
- Are there parallel truths across config, local manifest, runtime cache, or coordinator service?

## Mutation Discipline

- Can local code mutate replicated metadata without going through apply or consensus?
- Are admin paths narrower and more constrained than normal writes?

## Recovery

- What happens on missing or corrupt local state?
- Does startup fail fast, repair silently, or diverge?
- Can a restarted node serve stale or unsafe state before catch-up completes?

## Control Plane

- What happens if the coordinator or PD is unavailable after startup?
- Is freshness explicit or hidden behind retries and stale caches?
- Are lease transfer and allocator lower bounds rooted in one authority?

## Lifecycle

- Is shutdown gated explicitly?
- Do request contexts propagate end-to-end?
- What happens on queue overflow, deadline expiry, or transport drop?
