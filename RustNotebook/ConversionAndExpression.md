# Conversion AND Expressions

Conversion between custom types is done through traits.

---

## From and Into

The `From` and `Into` traits are linked together so that you can convert Type A to Type B and vice versa.

### From

The `From` trait is used to create a custom type from another type, you can do this by implementing the `From` trait.

```rust
use std::convert::From;

impl From<T> for U {
    fn from(t: T) -> U {
        // Code to convert from T to U
    }
}
```

### Into

If you implement the From trait you will be able to use the `into` method to convert from one type to another. You do have to specify the type you want to convert to.

---

## TryFrom and TryInto

These two functions are more generic as opposed to the `From` and `Into` traits. They return `Result`s which can be either `Ok` or `Err`.

To implement these traits you need to import the `TryFrom` and `TryInto` traits.

```rust
use std::convert::TryFrom;
use std::convert::TryInto;
```

---

## To and from Strings

### Converting to string

To implement the `.to_string()` method you need to implement the `Display` trait.

### Parsing a string

To parse a integer into a string is with the `parse` method.

```rust
let parsed: i32 = "5".parse().unwrap();
let <variable>: <type> = "<string>".parse().unwrap();
```

To parse a string into a type you need to implement the `FromStr` trait into the custom type.

---
---

## **Expressions**

Expression end with `;`.

To declare a variable use the `let` keyword.

Blocks are expressions too, so they can be used to assign variables. However the last expression in the block will need to be ended without a `;` or the variable will not be assigned.
