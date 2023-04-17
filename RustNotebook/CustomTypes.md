# Custom Types

The two data type creators in rust are:

- `struct` which is a structure
- `enum` which is an enumeration (allows it to be used a predefined set of constants)

`const` and `static` are also used to declare constants but they are not data type creators.

---

## Structures

There are three types of structures in rust:

- Tuple Struct (named tuples)
- Unit Struct (generic structures)
- C struct (The way C uses structures)

Structures can be reused inside other structures as well.
To define a variable as a structure use `{}` to input the the values that the structure needs.
When just calling a function use `()` for the parameters.

---

## Enums

Any variant of Structures can be used as an enum variant.
If defining an enum with multiple variants, you can set them up through `{}` and then if the variant takes in an argument through its `()` then you can access it like that.

>`match` keyword can be used to find the particular enum type that needs to be used if you have multiple variants within one enum.

### Type Aliases

If a name of a enum is too long then using `type <name> = <enum type>` can be used to shorten the name of the enum. The most common alias is the `self` alias used within functions.

### use

The `use` declaration can be used so manual scoping isn't needed.

> `#![allow(dead_code)]` is used to hide warnings for unused code

### C-like

Enum variants can be set up to be like C enums with the index of the enum being the value of the enum.

### Testcase: Linked-List

Using `impl` you can set up a class like function system with the `enum` being the variables that are going to be used.

---

## Constants

`Const`: unchangeable value  
`Static`: possibly mutable variable with "static" lifetime

>Global Variables are declared outside of all other scopes  
>You can put if else statements inside of print statements for formatting purposes
