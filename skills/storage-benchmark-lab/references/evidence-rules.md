# Evidence Rules

## Start With A Claim

The benchmark exists to support a claim such as:
- lower read amplification
- faster recovery
- lower tail latency under compaction
- safer degraded-mode behavior

If there is no claim, there is no benchmark design yet.

## Workload Axes

Record:
- key and value sizes
- distribution and skew
- read/write mix
- batch size
- concurrency
- warm/cold state
- durability mode

## Baselines

A good baseline is:
- functionally comparable
- configured fairly
- measured on the same hardware and runtime envelope

If semantics differ, explain the gap before showing numbers.

## Mandatory Caveats

Always call out:
- unsupported workload classes
- effects of caches or prefetch
- background compaction or GC assumptions
- whether degraded or recovery mode was excluded
