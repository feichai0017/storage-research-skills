# Workflow Funnel

Use this as the main checklist when triaging an idea.

## Gate 1: Is It A Real Problem?

Ask:
- Which users, operators, or systems pay this cost?
- Is the pain correctness, recovery, scalability, latency, maintenance, or operability?
- Can you point to an actual workload, bug class, or repeated design tension?
- Would a strong engineer building the current system say "yes, this is painful"?

Red flags:
- the problem exists only after stacking artificial assumptions
- the pain disappears once the scope is narrowed properly
- the problem is mostly naming or taxonomy

## Gate 2: Has It Already Been Done?

Search:
- top systems and database venues
- core protocol venues when the idea smells like coordination or consensus
- representative industrial systems

Judge overlap on:
- problem statement
- core mechanism
- claim boundary
- evaluation style

If a prior system or paper already owns most of the same claim, do not pretend your naming changes make it new.

## Gate 3: Can We Build It?

Ask:
- what artifact is needed to test the first real claim?
- what codebase or prototype base exists?
- what is the minimum system slice needed?
- what pieces are risky or blocked on missing infra?

Good sign:
- you can reach a falsifiable result without building the entire dream system

## Gate 4: Can We Evaluate It?

Ask:
- what baseline is fair?
- what workload shows the pressure?
- what failure surface matters?
- what evidence would convince a skeptical reviewer?

If evaluation requires unavailable data, impossible scale, or fake baselines, the idea is weaker than it looks.

## Gate 5: Is The Contribution Deep Enough?

Ask:
- does the work change a real boundary or only refactor a known one?
- does it expose a new property, not just better packaging?
- does it answer a hard question the literature leaves fuzzy?
- is the evidence strong enough for the claimed depth?

## Gate 6: Where Does It Belong?

Map the hardest contribution:
- systems boundary and recovery semantics
- storage engine mechanism
- query or transaction/data-management mechanism
- protocol or proof burden

Use that to set the likely venue family.

## Gate 7: Final Decision

- `GO` if the problem is real, overlap is manageable, and evidence looks feasible
- `PIVOT` if the problem is real but the contribution boundary is weak
- `KILL` if the idea is fake, redundant, or too expensive for likely payoff
