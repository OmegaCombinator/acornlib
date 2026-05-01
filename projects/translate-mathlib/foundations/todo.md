# Foundations and Set-Theoretic Infrastructure

Goal: make core definitions and proof patterns stable enough that later libraries can build on them without constant local patching.

- [ ] [Infrastructure for transporting structure across equality and equivalence](transport-across-equality/todo.md)
- [ ] [Relation algebra for reflexive, symmetric, transitive, and equivalence relations](relation-algebra/todo.md)
- [ ] [Canonical APIs for products, sums, options, and dependent pairs](core-type-constructions/todo.md)
- [ ] [Quotient constructions with good elimination and equality lemmas](quotients/todo.md)

## Current Focus

Foundational quotient API is now committed to the existing `Quotient`/`QuotientOver`/`QuotientRelation` family in `src/equivalence.ac`; subobject transport across the quotient projection is in place. Remaining quotient work is to build group/ring/module quotients and kernel-relation APIs on top of this foundation. Core type construction refactors remain deferred until their API choices are settled.
