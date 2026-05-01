# Algebraic Quotients

Goal: build group, ring, and module quotient APIs on top of the foundational `Quotient` / `QuotientOver` family, starting from kernel-of-homomorphism congruences.

- [ ] Lift `+` and `-` through the additive quotient (define an `AddGroup` instance on `Quotient[A]` modulo the kernel of an `AddGroupHom`)
- [ ] Bridge `MonoidHom` and `GroupHom` kernels to multiplicative congruences and lift the operation
- [ ] Combine additive and multiplicative kernels for ring homomorphisms
- [ ] Lift module structure through a module-hom kernel
- [ ] Define a foundational additive subgroup API and the quotient-by-additive-subgroup construction
- [ ] Define a normal subgroup API and the general group quotient `G/N`

Status:

- `add_monoid_hom_kernel_respects_add` and `add_monoid_hom_kernel_is_add_congruence` in `src/quotient_algebra.ac` give the additive monoid bridge.
- `add_group_hom_kernel_respects_add`, `add_group_hom_kernel_respects_neg`, and `add_group_hom_kernel_is_add_congruence` in `src/quotient_algebra.ac` give the additive group bridge (taking an `AddGroupHom[A, B]` so the existing `add_group_hom_add` / `add_group_hom_neg` / `add_group_hom_zero` lemmas apply directly; the predicate-level form `is_add_group_hom` was attempted first but the direct identity proofs timed out under default search).
