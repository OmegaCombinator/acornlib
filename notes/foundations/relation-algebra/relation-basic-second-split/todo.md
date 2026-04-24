# Split `relation_basic.ac`

Goal: keep bare relation algebra separate from function-based transport, so foundational imports can stay lighter and later APIs have clearer layering.

- [ ] Audit which declarations in `src/relation_basic.ac` are genuinely basic relation algebra
- [ ] Audit which declarations in `src/relation_basic.ac` are pullback and transport lemmas
- [ ] Fix the target boundary so `src/relation_basic.ac` no longer needs function-transport imports except where mathematically unavoidable
- [ ] Create `src/relation_transport.ac` for pullback, compatibility, and injective or surjective reflection lemmas
- [ ] Move `relation_pullback` and `respects_equivalence` into the transport module
- [ ] Move pullback preservation lemmas for reflexive, symmetric, transitive, and total relations into the transport module
- [ ] Move injective and surjective reflection lemmas into the transport module
- [ ] Update `src/relation.ac`, `src/order_relation.ac`, and `src/set.ac` to import the new transport module directly
- [ ] Reduce `src/relation_basic.ac` to bare relation algebra, closures, and equivalence-style stepping lemmas
- [ ] Remove this branch once the split verifies cleanly

## Current Focus

The first step is the boundary audit, because the second split should sharpen layering rather than just rename one large file.
