# Relation Compatibility Under Functions

Goal: make it easy to transport relations along functions and to state compatibility of functions with relational structure.

- [ ] [Injective pullback lemmas for equality and reflexive closure](injective-pullbacks/todo.md)
- [ ] Add pullback lemmas for antisymmetry and order-style relations along injective maps
- [ ] Transfer equivalence relations across bijections
- [ ] Add bijective transport lemmas that pair pullbacks with future pushforward-style APIs
- [ ] Refactor one downstream proof outside `util.ac` to use the function-compatibility API
- [ ] Audit whether order-theoretic monotone-map work should reuse these relation transports
- [ ] Decide whether any closure-operator theorem beyond symmetric closure needs extra hypotheses
- [ ] Decide whether to add a pushforward relation API or defer it
- [ ] Add pushforward lemmas along surjective functions if that API is chosen
- [ ] Connect any future pushforward API back to `respects_equivalence`
- [ ] Add a first downstream user for these transports in the order-theory branch

## Current Focus

The active frontier is [injective-pullbacks](injective-pullbacks/todo.md).
