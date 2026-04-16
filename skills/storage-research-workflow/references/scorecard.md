# Research Scorecard

Use this scorecard for fast, repeatable triage.
The point is not false precision. The point is to force comparable judgments across ideas.

## Dimensions

Score each dimension from 1 to 5.

### 1. Problem Reality

- 1: vague or fake problem; mostly aesthetic or naming-driven
- 2: some real pain, but weak evidence that it matters broadly
- 3: real pain for a narrow workload, system class, or operator group
- 4: clear recurring pain in known systems or literature
- 5: important and undeniable problem with broad systems relevance

### 2. Prior-Art Risk

Interpret this as a reverse score where higher is better for the idea.

- 1: prior work or systems already occupy nearly the same claim
- 2: heavy overlap; hard to argue more than incremental difference
- 3: noticeable overlap, but a plausible boundary difference exists
- 4: manageable overlap; contribution boundary is fairly distinct
- 5: low overlap; claim boundary looks genuinely fresh

### 3. Feasibility

- 1: blocked by missing infra, impossible baseline, or unrealistic proof burden
- 2: possible in theory, but too expensive before first falsifiable result
- 3: feasible with focused scope and careful sequencing
- 4: feasible with current codebase, tools, and experimental plan
- 5: highly feasible; first strong result is reachable quickly

### 4. Novelty

- 1: engineering cleanup or repackaging only
- 2: narrow twist on a known mechanism
- 3: bounded but real contribution
- 4: strong architectural or systems contribution
- 5: unusually sharp contribution that changes how the boundary is understood

### 5. Venue Band

This is still scored 1 to 5, but each score maps to a paper band.

- 1: design note / internal memo / blog
- 2: workshop / preprint / early paper
- 3: FAST / ATC / EuroSys / ICDE range
- 4: strong conference contender in the relevant family
- 5: top-tier contender such as SOSP / OSDI / NSDI / SIGMOD / VLDB, if evidence lands

## Output Format

Return the scorecard in this shape:

```text
Scorecard
- Problem reality: X/5
- Prior-art risk: X/5
- Feasibility: X/5
- Novelty: X/5
- Venue band: X/5
```

Then add one short sentence per dimension explaining why the score is not higher.

## Interpretation Rule

- strong `GO`: mostly 4-5, with no dimension below 3
- cautious `GO`: mixture of 3-4, with a believable path to de-risk the weakest dimension
- `PIVOT`: one or two dimensions at 2, but the core problem is still real
- `KILL`: problem reality 1-2, or prior-art risk 1-2 with weak novelty, or feasibility 1-2 with no practical path
