# Category Theory

Goal: provide the categorical abstractions that Mathlib uses to organize large mathematical theories.

## Functors and Natural Transformations

- [ ] Add `swap` and `is_iso_pair` propagation theorems for natural-isomorphism pairs (deferred: per-x swap proof times out; symmetry of `is_iso_pair` chains through `nat_trans_dst_cat_eq` resists factoring)
- [ ] Define `CategoryEquivalence` structure bundling forward/backward functors with unit/counit natural isomorphisms
- [ ] Add vertical composition of natural transformations (deferred: prover times out on `d.dst(d.compose(b, a)) = beta.dst_functor.obj_map(x)` chain; the symmetric `src` case verifies, but `dst` resists every factoring tried so far - needs further lemma decomposition)
- [ ] Add horizontal composition of natural transformations

## Universal Constructions

- [ ] Implement limits and colimits
- [ ] Add adjunctions and universal constructions
- [ ] Support monads and comonads
- [ ] Build Yoneda, representability, and presheaf basics
- [ ] Add functor categories and standard categorical constructions

## Specialized Categories

- [ ] Introduce monoidal categories and related structure
- [ ] Add abelian-category infrastructure for later homological algebra
