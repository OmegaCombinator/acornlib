# Order-Relation API

Goal: treat order relations as first-class examples of the relation-algebra API, especially for converse, closure, and pullback transport.

- [ ] Refactor at least one theorem to use the new order-relation API
- [ ] Collapse this leaf once the closure and converse API is in place

Status:

- `src/util.ac` now has the general relation predicates `is_irreflexive`, `is_asymmetric`, and `is_total`, together with converse and pullback transport theorems.
- `src/order_relation.ac` now packages converse, relation-property, closure, and pullback theorems for `<=`, `>=`, `<`, and `>`.
- The remaining work in this leaf is no longer API construction; it is finding the first honest external user of that API.
