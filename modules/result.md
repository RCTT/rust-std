# [std::result](https://doc.rust-lang.org/std/result/index.html)

## Error handling with the Result type.

Result<T, E> is the type used for returning and propagating errors. It is an enum with the variants, Ok(T), representing success and containing a value, and Err(E), representing error and containing an error value.


```rust
enum Result<T, E> {
   Ok(T),
   Err(E),
}
```

Functions return Result whenever errors are expected and recoverable. In the std crate, Result is most prominently used for I/O.

A simple function returning Result might be defined and used like so:


```rust
#[derive(Debug)]
enum Version { Version1, Version2 }

fn parse_version(header: &[u8]) -> Result<Version, &'static str> {
    match header.get(0) {
        None => Err("invalid header length"),
        Some(&1) => Ok(Version::Version1),
        Some(&2) => Ok(Version::Version2),
        Some(_) => Err("invalid version"),
    }
}
```

let version = parse_version(&[1, 2, 3, 4]);
match version {
    Ok(v) => println!("working with version: {:?}", v),
    Err(e) => println!("error parsing header: {:?}", e),
}Run
Pattern matching on Results is clear and straightforward for simple cases, but Result comes with some convenience methods that make working with it more succinct.

```rust
let good_result: Result<i32, i32> = Ok(10);
let bad_result: Result<i32, i32> = Err(10);

// The `is_ok` and `is_err` methods do what they say.
assert!(good_result.is_ok() && !good_result.is_err());
assert!(bad_result.is_err() && !bad_result.is_ok());

// `map` consumes the `Result` and produces another.
let good_result: Result<i32, i32> = good_result.map(|i| i + 1);
let bad_result: Result<i32, i32> = bad_result.map(|i| i - 1);

// Use `and_then` to continue the computation.
let good_result: Result<bool, i32> = good_result.and_then(|i| Ok(i == 11));

// Use `or_else` to handle the error.
let bad_result: Result<i32, i32> = bad_result.or_else(|i| Ok(i + 20));

// Consume the result and return the contents with `unwrap`.
let final_awesome_result = good_result.unwrap();

```

## Results must be used
A common problem with using return values to indicate errors is that it is easy to ignore the return value, thus failing to handle the error. Result is annotated with the #[must_use] attribute, which will cause the compiler to issue a warning when a Result value is ignored. This makes Result especially useful with functions that may encounter errors but don't otherwise return a useful value.

Consider the write_all method defined for I/O types by the Write trait:

```rust
use std::io;

trait Write {
    fn write_all(&mut self, bytes: &[u8]) -> Result<(), io::Error>;
}
```

>Note: The actual definition of Write uses io::Result, which is just a synonym for Result<T,io::Error>.

This method doesn't produce a value, but the write may fail. It's crucial to handle the error case, and not write something like this:

```rust
use std::fs::File;
use std::io::prelude::*;

let mut file = File::create("valuable_data.txt").unwrap();
// If `write_all` errors, then we'll never know, because the return
// value is ignored.
file.write_all(b"important message");
```


If you do write that in Rust, the compiler will give you a warning (by default, controlled by the unused_must_use lint).

You might instead, if you don't want to handle the error, simply assert success with expect. This will panic if the write fails, providing a marginally useful message indicating why:

```rust
use std::fs::File;
use std::io::prelude::*;

let mut file = File::create("valuable_data.txt").unwrap();
file.write_all(b"important message").expect("failed to write message");
```

You might also simply assert success:

```rust
assert!(file.write_all(b"important message").is_ok());
```

Or propagate the error up the call stack with ?:

```rust
fn write_message() -> io::Result<()> {
    let mut file = File::create("valuable_data.txt")?;
    file.write_all(b"important message")?;
    Ok(())
}
```


### The question mark operator, ?

When writing code that calls many functions that return the Result type, the error handling can be tedious. The question mark operator, ?, hides some of the boilerplate of propagating errors up the call stack.

It replaces this:

```rust
use std::fs::File;
use std::io::prelude::*;
use std::io;

struct Info {
    name: String,
    age: i32,
    rating: i32,
}

fn write_info(info: &Info) -> io::Result<()> {
    // Early return on error
    let mut file = match File::create("my_best_friends.txt") {
           Err(e) => return Err(e),
           Ok(f) => f,
    };
    if let Err(e) = file.write_all(format!("name: {}\n", info.name).as_bytes()) {
        return Err(e)
    }
    if let Err(e) = file.write_all(format!("age: {}\n", info.age).as_bytes()) {
        return Err(e)
    }
    if let Err(e) = file.write_all(format!("rating: {}\n", info.rating).as_bytes()) {
        return Err(e)
    }
    Ok(())
}
```

With this:

```rust
use std::fs::File;
use std::io::prelude::*;
use std::io;

struct Info {
    name: String,
    age: i32,
    rating: i32,
}

fn write_info(info: &Info) -> io::Result<()> {
    let mut file = File::create("my_best_friends.txt")?;
    // Early return on error
    file.write_all(format!("name: {}\n", info.name).as_bytes())?;
    file.write_all(format!("age: {}\n", info.age).as_bytes())?;
    file.write_all(format!("rating: {}\n", info.rating).as_bytes())?;
    Ok(())
}
```

It's much nicer!

Ending the expression with ? will result in the unwrapped success (Ok) value, unless the result is Err, in which case Err is returned early from the enclosing function.

? can only be used in functions that return Result because of the early return of Err that it provides.
