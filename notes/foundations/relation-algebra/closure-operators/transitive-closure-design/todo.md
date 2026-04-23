# Transitive Closure Design

Goal: choose a representation for transitive and reflexive-transitive closure that is mathematically useful in Acorn.

- [x] Survey the current library for any existing general transitive-closure machinery
- [ ] Confirm whether the first API should stay homogeneous-only
- [ ] Compare an inductive reachability encoding against an intersection-of-closed-supersets encoding
- [ ] Check which minimality theorems are easy under the intersection encoding
- [ ] Check whether elimination and path-style reasoning would be awkward under the intersection encoding
- [ ] Decide whether finite-chain witnesses can be encoded cleanly with existing `List` or sequence infrastructure
- [ ] Note any Acorn language features that would materially improve transitive-closure formalization
- [ ] Choose names for transitive and reflexive-transitive closure operators
- [ ] Pick the first implementation target that is likely to verify cleanly
- [ ] Collapse this leaf once the first implementation plan is concrete
