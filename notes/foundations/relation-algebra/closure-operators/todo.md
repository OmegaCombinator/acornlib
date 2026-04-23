# Relation Closure Operators

Goal: add standard relation closures in a way that later algebra and order libraries can reuse.

- [ ] [Transitive-closure design](transitive-closure-design/todo.md)

The reflexive and symmetric closure API is now in `src/util.ac` and verifies cleanly. The remaining work in this branch is deciding how far a general transitive-closure API can go in Acorn without inductive reachability support.
