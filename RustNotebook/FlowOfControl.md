# Flow of Control

---

## If/Else

The if-else statement does not need parentheses around the condition, but it does need curly braces around the code block.

```rust
if <boolean> {
    <code>
} else {
    <code>
}

```

---

## Loop

The `loop` keyword is used to create an infinite loop. The `break` keyword is used to exit the loop. The `continue` keyword is used to skip the current iteration of the loop.

```rust
loop {
    <code>
    if <boolean> {
        continue;
    }

    if <boolean> {
        break;
    }
}
```

### Nesting and Labels

Labels need to be used to differentiate the loops. The label is placed before the loop and the label is used with the `break` keyword. The label is the form of `'<label>`

```rust
'outer: loop {
    <code>
    'inner: loop {
        <code>
        if <boolean> {
            break 'outer;
        }
    }
}
```

### Returning from Loops

To return a value from a loop, you need to put it after the `break` keyword.

```rust
let result = loop {
    <code>
    if <boolean> {
        break <value>;
    }
}
```

---

## While

The `while` keyword is used to create a loop that runs while the condition is true.

```rust
while <boolean> {
    <code>
}
```

---

## For loops

### For and Range

`for in` contruct can be used to iterate through an iterator.

An example of an iterator is `a..b` which is a range from `a` to `b`. The `..` is exclusive and the `..=` is inclusive.

### For and Iterator

The different iterators are:

- `iter()` - iterates over elements of a collection
- `into_iter()` - iterates over elements of a collection and consumes the values that are being iterated over
- `iter_mut()` - iterates over elements of a collection and allows the values to be modified

---

## Match

Using the `match` keyword is the same as using the `switch` keyword in other languages with `_` being the default case and `=>` being the way to specify what to do in the case. ALL cases must be covered.

```rust
match <value> {
    <case> => <code>,
    <case> => <code>,
    _ => <code>,
}
```

If a value is repeated in the cases, it will be assigned to the first case that it is in.

### Destructing

#### tuples

A tuple can be destructed by using variables in the different indexes of the tuple, using `..` to ignore the index of the tuple, or using the type of the tuple to designate the value that is being compared against.

```rust

let triple = (1, 2, 3);

match triple {
    (1, ..) => <code>,// Only cares about the first index
    (.., 3) => <code>,// Only cares about the second index
    (1, x, y) => <code>, //Matching only with the first index and assigning x and y are the second and third index
    (1, .., 3) => <code>, // Only cares about the first and third index
    _ => <code> // Default case
}
```

#### Arrays/Slices

Array and Slices can be destructed in the same manner as a tuple but you cannot just straight up ignore some of the values that are being compared against. For the values you don't care about the value, you can use `_` for single and  `..` for multiple values. If you want to store the values of an array/slice inside another list entirely you can use the form `<array> @ ..`, this will then store the values that are not being compared against in the variable that is being assigned to. As with tuples, individual variables you can also assign variables like tuples. That variable structure can be used within a array or slice.

#### Enums

Very simple to deconstruct enums, just use the name of the enum and the values that are being compared against.

#### Pointers/References

Dereferencing uses `*`, while Destructuring uses `&`, `ref`, and `ref mut`.  

Using `&` will match the value of the pointer/reference, while `ref` will match the value of the pointer/reference and store it in a variable. `ref mut` will do the same as `ref` but it will allow the value to be modified. `&` is used on the value side and `ref` and `ref mut` are used on the variable side.

#### Struct

Like enums and arrays you can deconstruct a struct by using the name of the struct and the values that are being compared against. All values of the struct need to be covered.

### Guards

After a match condition you can set secondary conditions that need to be met for the code to be executed. These are called guards and are set after the `if` keyword.

### Binding

You can bind values to variables by using the `@` symbol. This is done after the value that is being compared against.

```rust
match <value> {
    <case> => <code>,
    <variable> @ <case> => <code>,
}
```
---

## if let

If you don't need to match every case and the indentations can be too much the alternative is `if let`. It can be used to match variable types like:

```rust
if let <enum type> == <variable> {
    <code>
}
```

The `if let` also lets you find alternative failure cases by using `else` and `else if`.

---

## let-else

The `let-else` is used to check if a variable is a certain type and if it is not then it will execute the code in the `else` block.

> research more into this topic when you get the chance

---

## while let

The `while let` is used to check if a variable is a certain type and if it is not then it will exit the loop.
