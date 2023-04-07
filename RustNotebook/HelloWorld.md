# Hello World

## Comments

Comments are written like in C languages with `//` used for line comments and `/* */` for block commenting. For Block Coding there is no need for extra `*` when writing multiple lines.

---

## Formatted Printing

Printing in rust is done with macros and not functions, they are defined with `std::fmt`. The different types of macros are:

- `format!` - write text to a `String`
- `print!` - write text to the console (something like `format!`)
- `println!` - same as `print!` but adds a newline
- `eprint!` - writes text to the standard error (something like `print!`)
- `eprintln!` - same as `eprint!` but adds a newline

When formatting `{}` denotes an argument so in

```rust
println!("{} days", 31); 
```

the `{}` will be replaced with `31`. The `{}` can also denote the index of the argument so that if multiple `{}` are used in the same string, the arguments can be placed in the order of index. For example

```rust
println!("{0}, this is {1}. {1}, this is {0}", "Alice", "Bob"); 
```

will print `Alice, this is Bob. Bob, this is Alice.` The arguments inside `{}` can also contain variable names defined within the printing statements. Rust will check if the arguments are correct and will tell you to fix it.

Formats for number bases can be done with `:`, these are the different formats:  

- `:` - default (base 10)
- `:b` - binary
- `:o` - octal
- `:x` - hexadecimal (case of `x` determines case of output)

Formats for justification are using `<` and `>` with the way that the text is justified being determined by the number of spaces after the inequality sign and which way the inequality sign is pointing. `<` being left and `>` being right. To use a variable adjustment for the spaces append a `$` to the end of the number of spaces. For example

```rust
println!("{number:>width$}", number=1, width=6);  
```

will print `"000001"`. Additionally `^` can be used to center the text.

Formatting for decimal places is the same as in C languages with just the number format being `<variable_name/blank>:<magnitude>.<number of decimal places>`.

Overall all this formatting is under `std::fmt` with `fmt::Debug` using the notation `{:?}` for debugging and `fmt::Display` just having the regular `{}`

### Debug

To make something that allows for debugging print statements (structures and the like) add `#[derive(Debug)]` to the line before hand to make derive and allow for printing of the structure. This type of implementation is best if you don't want to implement the code for displaying yourself as this type of implementation works out the get-go
> There is a way to implement the code for formatting the debugged state but not quite sure how to explain it

### Display

To import do `use std::fmt;`  

For implementation purposes it would be done like  

```rust
impl fmt::Display for <name of structure>  {  
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
    write!(f, "{}", self.0)
    }
}
```

> If you specify in the beginning of your code that you are going ot be using the particular library like this:
>
>```rust
>use std::fmt::{self, Formatter, Display};
>```
>
> which turns:
>
> ```rust
>impl fmt::Display for <name of structure>{}
>```
>
>into:
>
>```rust
>impl Display for <name of structure>{}
>```

For ambiguous types you must first derive from debug then implement using display, basically the same as before but also use the debug derive.

#### Testcase: List

`write!` always outputs something even if thats an error so rust uses `?` at the end of a statement to test if it errors and return said error.

> To return something within a function, you don't use the return keyword like in other languages, you just don't put a semicolon on it.

### Formatting

You can also have structs be formatted in different ways depending on what the argument inside the `{}` is. Take:

```rust
#[derive(Debug)]
struct Vector2D{}
/*--------------------*/
impl fmt::Display for Vector2D
/*--------------------*/
impl fmt::Binary for Vector2D
```

The first will set up the Vector2d Structure to be displayed in a debug way.
The second will set up the Vector2d Structure to be displayed in a regular way.
Lastly, the third will set up the Vector2D Structure to be displayed in a binary format even though the Vector2D cannot be displayed as such.
