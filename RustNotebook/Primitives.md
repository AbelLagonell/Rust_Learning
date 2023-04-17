# Primitives

## Scalar Types

**Signed Integers**: `i8`, `i16`, `i32`, `i64`, `i128`, `isize` (pointer size)  
**Unsigned Integers**: `u8`, `u16`, `u32`, `u64`, `u128`, `usize` (pointer size)  
**Floating Point**: `f32`, `f64`  
**Boolean**: `bool`  
**Character**: `char` contains symbols too  
**Unit Type:** `()` empty tuple (but not a tuple)

>Default type for integers is `i32` and for floating point is `f64`

## Compound Types

**Arrays**: `[1 , 2, 3]`  
**Tuples**: `(1, true)`

---

## Literals and Operators

Integers, floats, booleans, and characters can be expressed using literals.
The `_` can be used to improve readability, such as `1_000` instead of `1000` or `0.000_001` instead of `0.000001`.
There is also support for scientific E-notation with the type that is actually being used being `f64`.
To put the number as a literal you do have to put what type of integer it is, if its alone.

> **LOGICAL OPERATORS**  
> `&&` is AND  
> `||` is OR  
> `!` is NOT  
> **BITWISE OPERATORS**  
> `&` is AND  
> `|` is OR  
> `^` is XOR  
> `>> <number>` is shift by that many bits to the right  
> `<< <number>` is shit by that many bits to the left  

---

## Tuples

Are constructed using `()`. They can be used as parameters or outputs like in python.
They can even be used for inputs to be formatted either by the tuple itself or by assigning multiple variables to the tuple.

>Any tuple with more than 12 elements cannot be printed

```rust
//Tuple of Tuples Printing
let tuple_of_tuples = ((1u8, 2u16, 2u32), (4u64, -1i8), -2i16);
println!("tuple of tuples: {:?}", tuple_of_tuples);
//Tuple Printing
let pair = (1, true);
println!("Pair is {:?}", pair);
//Deconstruction followed by printing
let tuple = (1, "hello", 4.5, true);
let (a, b, c, d) = tuple;
println!("{:}, {:?}, {:?}, {:?}", a, b, c, d);
```

When printing a tuple straight into the print statement to make sure that the compiler reads the integer or character, etc, as a tuple make sure to put a comma afterwards.

> Functions can use structures as parameters and as return types, just make sure to output them as a constructor being made for the class.
> Functions do need variable names in the parameters followed by `:` to signify the type of variable in question similar to python. The return type is also signified by `->` followed by the type of variable being returned.

---

## Arrays and Slices

Arrays are initialized with `[T; length]` with the length known at compilation time. You can also set them up to be initialized with the same value for each element with `[initial_value; length]`.
Slices are initialized with `&[T]` with the length being known at runtime. The slice does have a function to find the length of a particular slice, `len()`. Arrays can be analyzed as slices with `&array_name` or `&array_name[start_index .. end_index]`. End index is exclusive.

Arrays can be accessed using `.get` or `[]` with the index of the element in question. `.get` will return an `Option<&T>` while `[]` will return a `&T`. The `Option` type is an enum that is either `Some(&T)` or `None`. This is used to prevent null pointer exceptions. Inside the `Some(&T)` is the actual value of the element in question. Putting a variable there would then assign the value of the element to the variable.

>Iterators like the `for` loop can be formatted like this:
>
>```rust
>for i in 0..5 {} //0 to 4
>```
