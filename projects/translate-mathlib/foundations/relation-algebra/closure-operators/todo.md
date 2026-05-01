# Relation Closure Operators

Goal: add standard relation closures in a way that later algebra and order libraries can reuse.

- [ ] [Finite-path / walk objects on top of relation powers](finite-path-objects/todo.md)

The reflexive and symmetric closure API is in `src/relation_basic.ac` (re-exported from `src/util.ac`), and the first transitive / reflexive-transitive closure API is now in `src/relation.ac` using homogeneous Nat-indexed relation powers. The universal-property and monotonicity lemmas are in place for the transitive / reflexive-transitive variants, and all four closures (reflexive, symmetric, transitive, reflexive-transitive) now have monotonicity, fixed-point, and idempotence laws (`relation_reflexive_closure_monotone`, `relation_reflexive_closure_eq_self_of_reflexive`, `relation_reflexive_closure_idempotent`, the symmetric counterparts, `relation_trans_closure_eq_self_of_transitive`, `relation_trans_closure_idempotent`, `relation_refl_trans_closure_eq_self_of_reflexive_transitive`, and `relation_refl_trans_closure_idempotent`). `src/nat/nat_gcd.ac` is the first downstream use. The remaining work in this branch is a definition question about whether explicit path / walk objects should sit on top of the powers-based API.
