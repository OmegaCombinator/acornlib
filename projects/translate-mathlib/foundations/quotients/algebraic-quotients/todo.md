# Algebraic Quotients

Goal: build group, ring, and module quotient APIs on top of the foundational `Quotient` / `QuotientOver` family, starting from kernel-of-homomorphism congruences.

- [ ] Lift module structure through a module-hom kernel
- [ ] Define a foundational additive subgroup API and the quotient-by-additive-subgroup construction
- [ ] Define a normal subgroup API and the general group quotient `G/N`
- [ ] Introduce a dedicated `RingHom[R, S]` struct so the ring kernel bridges no longer need a paired `AddGroupHom`/`MonoidHom` with an equality side condition
- [ ] Lift `+`, `-`, and `*` through the kernel quotient as actual operations (deferred: a typeclass instance on `Quotient[A]` is blocked because the operation depends on `qrel`, which is value-level rather than type-level; a per-`qrel` `quotient_over_binary_op` lift already exists in `src/equivalence.ac` and is the path forward)

Status:

- `add_monoid_hom_kernel_respects_add` and `add_monoid_hom_kernel_is_add_congruence` in `src/quotient_algebra.ac` give the additive monoid bridge.
- `add_group_hom_kernel_respects_add`, `add_group_hom_kernel_respects_neg`, and `add_group_hom_kernel_is_add_congruence` in `src/quotient_algebra.ac` give the additive group bridge.
- `monoid_hom_kernel_respects_mul` and `monoid_hom_kernel_is_mul_congruence` give the multiplicative monoid bridge.
- `group_hom_kernel_respects_mul`, `group_hom_kernel_respects_inverse`, and `group_hom_kernel_is_mul_congruence` give the multiplicative group bridge.
- `ring_hom_kernel_respects_add`, `ring_hom_kernel_respects_mul`, `ring_hom_kernel_is_add_congruence`, `ring_hom_kernel_is_mul_congruence`, and `ring_hom_kernel_is_ring_congruence` give the ring bridge, taking a paired `AddGroupHom[R, S]` and `MonoidHom[R, S]` with `f.hom = g.hom` as the side condition. `is_ring_hom` and `is_ring_congruence` are defined in `src/quotient_algebra.ac`.
- All kernel bridges take struct-form homomorphisms (`AddGroupHom`, `MonoidHom`, `GroupHom`) so the existing `_add` / `_mul` / `_neg` / `_inv` / `_zero` / `_one` lemmas apply directly. A predicate-level form was attempted first but the identity-derivation proofs timed out under default search; the struct path is the durable choice.
