# Ordered-Group Audit

Goal: find the first ordered-group theorem that should use the new relation transport or order-relation API instead of local relation proofs.

- [ ] Audit `ordered_group.ac` for order-data transport opportunities
- [ ] Audit `add_ordered_group.ac` for order-data transport opportunities
- [ ] Audit subgroup-related ordered arguments for hidden transport patterns
- [ ] Identify whether any local `lt` theorem should be restated through the shared order API
- [ ] Pick one honest downstream consumer if it exists
- [ ] Refactor that theorem through the shared API if the refactor is cleaner
- [ ] Record if no current theorem benefits from the transport API yet
- [ ] Revisit after the order-relation API is larger
- [ ] Defer this leaf if the audit stays purely speculative
- [ ] Collapse this leaf once one real user is in place or the no-user conclusion is stable
