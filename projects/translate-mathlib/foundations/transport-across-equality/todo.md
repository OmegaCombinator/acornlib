# Transport Across Equality and Equivalence

Goal: support moving data and theorems across definitional boundaries in a controlled way.

Status:

- Relation property transport in `src/relation_basic.ac` now uses the shared binary-function equality transport API.
- Pullback distributes over union, intersection, and converse; pushforward distributes over union, commutes with converse, and lies inside the intersection of pushforwards (`relation_pullback_union`, `relation_pushforward_union`, `relation_pushforward_converse`, `relation_pushforward_intersection_subset` in `src/relation_transport.ac`).
- Quotient subobject transport API in `src/equivalence.ac`: `quotient_image_set` and `quotient_preimage_set` over the quotient projection, with pointwise membership lemmas (`quotient_image_set_contains_eq`, `quotient_preimage_set_contains_eq`, `quotient_preimage_image_contains_eq`), saturation preservation (`quotient_preimage_set_is_saturated`), one-sided containments (`quotient_image_preimage_subset`, `quotient_subset_preimage_image`, `saturated_preimage_image_subset`, `on_relation_subset_image_preimage`), and the full round-trip set equalities `quotient_preimage_image_of_saturated` and `quotient_image_preimage_on_relation` together with their pointwise iff forms (`saturated_preimage_image_iff`, `on_relation_image_preimage_iff`).
- Type-level equality is not currently exposed as a value-level equality form: `acorn verify - --read-only` reports that type parameters are not values in equality expressions.
