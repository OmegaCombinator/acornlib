# Category Theory

Goal: provide the categorical abstractions that Mathlib uses to organize large mathematical theories.

## Functors and Natural Transformations

- [ ] Support equivalences of categories
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
