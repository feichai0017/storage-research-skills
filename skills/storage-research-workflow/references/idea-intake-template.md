# Idea Intake Template

Use this template before scoring an idea.
If the user gives an unstructured thought, rewrite it into this form first.

## Intake

- Idea title:
- One-sentence idea:
- Target area:
  Examples: LSM engine, OLTP engine, OLAP engine, metadata service, distributed KV, control plane, consensus, snapshotting, query path, indexing.
- Problem type:
  Examples: correctness, recovery, latency, throughput, metadata scale, maintenance cost, degraded mode, operator pain, evaluation gap.
- Who feels the pain today:
- Concrete scenario or workload:
- Existing systems or papers likely related:
- What seems unsatisfactory in current designs:
- Proposed mechanism in one paragraph:
- Strongest hoped-for claim:
- What artifact would need to be built:
- What evidence would be needed:
- Likely baselines:
- Biggest risk or uncertainty:

## Intake Compression Rule

After filling the template, compress it into:
- problem statement
- contribution candidate
- proof or evidence burden

If the idea still cannot be compressed into those three lines, it is not ready for scoring.

## Fast Reject Hints

Reject or pivot early if:
- the user cannot name who feels the pain
- no concrete workload or failure mode is identified
- the proposed mechanism is mostly renaming an existing pattern
- there is no plausible baseline
- the hoped-for claim is much larger than the artifact that could realistically be built
