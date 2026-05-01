# Transport Across Equality and Equivalence

Goal: support moving data and theorems across definitional boundaries in a controlled way.

- [ ] Strengthen quotient subobject transport to full round-trip equalities (`quotient_preimage_image_of_saturated`, `quotient_image_preimage_on_relation`); current pointwise lemmas are present but the set-extensionality-level equalities currently time out under default search.

Status:

- Relation property transport in `src/relation_basic.ac` now uses the shared binary-function equality transport API.
- Pullback distributes over union, intersection, and converse; pushforward distributes over union, commutes with converse, and lies inside the intersection of pushforwards (`relation_pullback_union`, `relation_pushforward_union`, `relation_pushforward_converse`, `relation_pushforward_intersection_subset` in `src/relation_transport.ac`).
- Quotient subobject transport API in `src/equivalence.ac`: `quotient_image_set` and `quotient_preimage_set` over the quotient projection, with pointwise membership lemmas (`quotient_image_set_contains_eq`, `quotient_preimage_set_contains_eq`, `quotient_preimage_image_contains_eq`), saturation preservation (`quotient_preimage_set_is_saturated`), and one-sided round-trip lemmas (`quotient_image_preimage_subset`, `quotient_subset_preimage_image`).
- Type-level equality is not currently exposed as a value-level equality form: `acorn verify - --read-only` reports that type parameters are not values in equality expressions.
