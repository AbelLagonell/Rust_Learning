# Types

---

## Casting

There is no implicit type conversion but there is explicit type conversion with `as`.
Alternatively, you can use `<number>.to_int_unchecked()::<[type of number]>()` to do the same thing but without the bounds checking.
When casting any value to an unsigned type, T, `T::MAX + 1` is added or subtracted until the value fits into the new type.
When casting to a signed type, the (bitwise) result is the same as first casting to the corresponding unsigned type. If the most significant bit of that value is 1, then the value is negative.

---

## Literals

Numeric Literals can be type annotated by adding the type as a suffix. If there is on type specified, the compiler will use i32 for integers and f64 for floating point numbers.

---

## Inference

The compiler can infer what type we want to use based on the value and how we use it. So if the value is not initialized from the get go eventually the compiler will figure out what type it is.

---

## Aliasing

`type` statements can give names to existing types. All of these renames have to be in the form of `UpperCamelCase`, the only exceptions to the rule are primitive types.

Mainly used to reduce boilerplate. Or functions that will be used the same way over and over again.
