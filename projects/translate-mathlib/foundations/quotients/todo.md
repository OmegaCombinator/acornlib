# Quotient Constructions

Goal: support quotient objects as first-class foundational tools using equivalence-class constrained structures instead of one-off encodings.

- [ ] Add quotient constructions for groups, rings, and modules on top of the chosen API
- [ ] Add APIs for kernel relations and quotient-by-kernel constructions
- [ ] Audit where current code is hand-simulating quotients and record migration targets

Status:

- Foundational quotient API is the existing `Quotient[T]` / `QuotientOver[T]` / `QuotientRelation[T]` family in `src/equivalence.ac`: equivalence-class constrained structures with `quotient_projection`, `quotient_lift`, `quotient_unary_respects`, `quotient_binary_respects`, and induced congruence lemmas. `src/zmod.ac` is the first downstream user.
- Subobject transport across the quotient projection lives in `src/equivalence.ac` (`quotient_image_set`, `quotient_preimage_set`, plus saturation preservation and pointwise lemmas).
