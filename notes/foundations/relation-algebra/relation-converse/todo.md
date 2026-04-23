# Relation Converse

Goal: make converse/inverse-style relation operations reusable instead of restated ad hoc.

This leaf is complete enough for now. `src/util.ac` now has converse, involutive, composition-reversal, monotonicity, and symmetry/equivalence compatibility lemmas, and `src/set.ac` has a downstream proof refactored to use the converse API. No separate `inverse relation` naming is needed beyond `relation_converse` at this stage.
