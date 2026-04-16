# Storage Implementation Checklist

## Boundary

- What is authoritative here?
- Which state is cached, derived, or advisory?
- Where does ownership of memory and file handles live?

If this is not an LSM engine, also ask:
- what is the authoritative page, extent, segment, or catalog structure?
- what is the checkpoint or flush boundary?

## Durability

- Is the write protocol explicit?
- If metadata changes, is the sequence `write temp -> fsync temp -> rename -> fsync parent dir` required?
- After sync failure, is the object poisoned or still incorrectly serviceable?

## Recovery

- What happens on open if state is missing or corrupt?
- Is recovery strict by default?
- Are there silent repairs or dropped entries that should fail startup instead?

## Hot Path

- Are there avoidable copies?
- Is there hidden I/O or allocation?
- Did the change alter visibility or iterator semantics?
- Did the change alter page-cache, buffer-pool, extent-map, or object-index behavior?

## Tests

- startup failure on missing/corrupt file
- crash or fault injection on publish boundary
- recovery regression
- shutdown/lifecycle regression
