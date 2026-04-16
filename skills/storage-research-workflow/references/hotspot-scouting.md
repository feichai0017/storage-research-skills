# Hotspot Scouting

Use this reference when the user asks for directions instead of presenting an idea.

## Goal

Find repeated systems pressure from public research signals.
Do not chase keywords. Chase recurring bottlenecks, semantic gaps, and deployment pain.

## Where To Look

Prioritize primary sources:
- accepted paper lists from top venues
- official conference programs
- workshop programs
- CFP topic lists
- keynotes
- serious open-source system issue trackers and design docs

Suggested venue families:
- databases: SIGMOD, VLDB, CIDR, ICDE
- systems/storage: SOSP, OSDI, NSDI, EuroSys, FAST, ATC
- protocols/distributed algorithms: PODC, DISC

## Scouting Workflow

1. Scan the last 1-2 years of public venue signals.
2. Cluster recurring themes.
3. For each theme, separate:
   - hot keyword
   - underlying systems pressure
   - likely artifact class
4. Keep only themes that map to a concrete system problem.

## What Counts As A Good Hotspot

A good hotspot has at least two of:
- multiple recent papers from top venues
- visible industrial/open-source adoption pressure
- repeated benchmark or deployment pain
- unresolved semantics, not just performance tuning

## What Does Not Count

- one flashy paper with no visible follow-on
- a trend whose papers are mostly wrappers around foundation models
- topics that require giant infrastructure before a single falsifiable result

## Output

Return:
- hotspot label
- why it is hot
- underlying systems pressure
- 2-3 concrete idea directions
