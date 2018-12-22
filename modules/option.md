## std::option

### Optional values.

Type Option represents an optional value: every Option is either Some and contains a value, or None, and does not. Option types are very common in Rust code, as they have a number of uses:


- Initial values
- Return values for functions that are not defined over their entire input range (partial functions)
- Return value for otherwise reporting simple errors, where None is returned on error
- Optional struct fields
- Struct fields that can be loaned or "taken"
- Optional function arguments
- Nullable pointers
- Swapping things out of difficult situations

Options are commonly paired with pattern matching to query the presence of a value and take action, always accounting for the None case.

```rs
fn divide(numerator: f64, denominator: f64) -> Option<f64> {
    if denominator == 0.0 {
        None
    } else {
        Some(numerator / denominator)
    }
}

// The return value of the function is an option
let result = divide(2.0, 3.0);

// Pattern match to retrieve the value
match result {
    // The division was valid
    Some(x) => println!("Result: {}", x),
    // The division was invalid
    None    => println!("Cannot divide by 0"),
}
```

### Options and pointers ("nullable" pointers)
Rust's pointer types must always point to a valid location; there are no "null" pointers. Instead, Rust has optional pointers, like the optional owned box, `Option<Box<T>>`.

The following example uses `Option` to create an optional box of `i32`. Notice that in order to use the inner `i32` value first, the check_optional function needs to use pattern matching to determine whether the box has a value (i.e. it is `Some(...)`) or not (`None`).

```rs
let optional = None;
check_optional(optional);

let optional = Some(Box::new(9000));
check_optional(optional);

fn check_optional(optional: Option<Box<i32>>) {
    match optional {
        Some(ref p) => println!("has value {}", p),
        None => println!("has no value"),
    }
}
```

This usage of Option to create safe nullable pointers is so common that Rust does special optimizations to make the representation of Option<Box<T>> a single pointer. Optional pointers in Rust are stored as efficiently as any other pointer type.

### Examples
Basic pattern matching on Option:

```rs
let msg = Some("howdy");

// Take a reference to the contained string
if let Some(ref m) = msg {
    println!("{}", *m);
}

// Remove the contained string, destroying the Option
let unwrapped_msg = msg.unwrap_or("default message");
```

Initialize a result to None before a loop:

```rs
enum Kingdom { Plant(u32, &'static str), Animal(u32, &'static str) }


// A list of data to search through.
let all_the_big_things = [
    Kingdom::Plant(250, "redwood"),
    Kingdom::Plant(230, "noble fir"),
    Kingdom::Plant(229, "sugar pine"),
    Kingdom::Animal(25, "blue whale"),
    Kingdom::Animal(19, "fin whale"),
    Kingdom::Animal(15, "north pacific right whale"),
];

// We're going to search for the name of the biggest animal,
// but to start with we've just got `None`.
let mut name_of_biggest_animal = None;
let mut size_of_biggest_animal = 0;
for big_thing in &all_the_big_things {
    match *big_thing {
        Kingdom::Animal(size, name) if size > size_of_biggest_animal => {
            // Now we've found the name of some big animal
            size_of_biggest_animal = size;
            name_of_biggest_animal = Some(name);
        }
        Kingdom::Animal(..) | Kingdom::Plant(..) => ()
    }
}

match name_of_biggest_animal {
    Some(name) => println!("the biggest animal is {}", name),
    None => println!("there are no animals :("),
}
```

### Structs


- [IntoIter](https://doc.rust-lang.org/std/option/struct.IntoIter.html)	An iterator over the value in Some variant of an Option.
- [Iter](https://doc.rust-lang.org/std/option/struct.Iter.html)	An iterator over a reference to the Some variant of an Option.
- [IterMut](https://doc.rust-lang.org/std/option/struct.IterMut.html)	An iterator over a mutable reference to the Some variant of an Option.
- [NoneError](https://doc.rust-lang.org/std/option/struct.NoneError.html)	[Experimental] The error type that results from applying the try operator (?) to a None value. If you wish to allow x? (where x is an Option<T>) to be converted into your error type, you can implement impl From<NoneError> for YourErrorType. In that case, x? within a function that returns Result<_, YourErrorType> will translate a None value into an Err result.

### Enums
Option	The Option type. See [the module level documentation](https://doc.rust-lang.org/std/option/index.html) for more.
