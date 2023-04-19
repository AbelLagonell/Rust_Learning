# Variable Bindings

The `let` keyword is used to assign variables in rust. The actual type of the variable is inferred by the compiler. To make sure that the compiler does not put a warning with unused variables put an `_` in front of the variable name.

---

## Mutability

From the get go variables are immutable, to make them mutable add `mut` in front of the variable name.

---

## Scope and Shadowing

Like in most languages the variable is constrained to where it was declared. Rust also allows for shadowing of variables, which is basically redeclaring a variable in the same scope. This is done by using the `let` keyword again.

---

## Declare First

Variables can be declared but not initialized. This is done by using the `let` keyword without a value. Rust does not like this since using an uninitialized variable is a runtime error.

---

## Freezing

When data is bound by the same name immutably, it freezes. Meaning that the shadowed variable nor the local variable can change their value since they are bound to the same name.
