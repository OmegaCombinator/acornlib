# Discrete Order Audit

Goal: find the first arithmetic-order theorem that should use the relation transport or order-relation API instead of local relation proofs.

- [ ] Audit `nat/nat_base.ac` for relation-style order arguments
- [ ] Audit `nat` order-adjacent files for closure-style reasoning over `<=` or `<`
- [ ] Audit `rat/rat_base.ac` for transport-style order proofs
- [ ] Audit `int/lattice.ac` for transport-style order proofs
- [ ] Identify whether any existing closure theorem can be rewritten through the shared API
- [ ] Pick the strongest honest downstream consumer from those audits
- [ ] Refactor that theorem through the shared API if the result is cleaner
- [ ] Record if the audit only exposes future opportunities
- [ ] Defer this leaf if there is no immediate consumer
- [ ] Collapse this leaf once one real user is in place or the no-user conclusion is stable
