# Category Theory

Goal: provide the categorical abstractions that Mathlib uses to organize large mathematical theories.

## Functors and Natural Transformations

- [ ] Finish vertical composition: prove `vertical_compose_component` satisfies `is_natural_transformation` and bundle as `vertical_compose_nat_trans`. Predicate, component, and shared-category lemmas are already in place; the endpoint and naturality lemmas hit prover timeouts when chasing structure-field equalities and need smaller helper lemmas.
- [ ] Add horizontal composition of natural transformations
- [ ] Support equivalences of categories

## Universal Constructions

- [ ] Implement limits and colimits
- [ ] Add adjunctions and universal constructions
- [ ] Support monads and comonads
- [ ] Build Yoneda, representability, and presheaf basics
- [ ] Add functor categories and standard categorical constructions

## Specialized Categories

- [ ] Introduce monoidal categories and related structure
- [ ] Add abelian-category infrastructure for later homological algebra
