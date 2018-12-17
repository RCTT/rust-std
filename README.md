# rust-std

Rust 标准库中文翻译。欢迎大家参与进来，也欢迎大家加入 **RCTT** (Rust Chinese Translation Team)，在本仓库提交 issue 即可，我会及时主动邀请你。

QQ交流群：962057386

---

## 相关

更多请看 [Rust 标准库官方文档](https://doc.rust-lang.org/std/)，鉴于译者水平有限，如有疑问欢迎提出^_^ 。

## rust 标准库之旅

本文档致力于指出Rust标准库的显著特性。

### 容器与集合类型


- [Vec<T>]() - A heap-allocated vector that is resizable at runtime.
- [[T; n]]() - An inline array with a fixed size at compile time.
- [[T]]() - A dynamically sized slice into any other kind of contiguous storage, whether heap-allocated or not.

Slices can only be handled through some kind of pointer, and as such come in many flavors such as:

- [&[T]]() - shared slice
- [&mut [T]]() - mutable slice
- [Box<[T]>]() - owned slice

### 基本类型

- [array]()	    A fixed-size array, denoted [T; N], for the element type, T, and the non-negative compile-time constant size, N.
- [bool]() 	    The boolean type.
- [char]() 	    A character type.
- [f32]() 	    The 32-bit floating point type.
- [f64]()     	The 64-bit floating point type.
- [fn]()      	Function pointers, like fn(usize) -> bool.
- [i8]() 	        The 8-bit signed integer type.
- [i16]() 	    The 16-bit signed integer type.
- [i32]()     	The 32-bit signed integer type.
- [i64]()     	The 64-bit signed integer type.
- [i128]()    	The 128-bit signed integer type.
- [isize]()       The pointer-sized signed integer type.
- [pointer]() 	Raw, unsafe pointers, *const T, and *mut T.
- [reference]()   References, both shared and mutable.
- [slice]() 	    A dynamically-sized view into a contiguous sequence, [T].
- [str]() 	    String slices.
- [tuple]()       A finite heterogeneous sequence, (T, U, ..).
- [u8]() 	        The 8-bit unsigned integer type.
- [u16]() 	    The 16-bit unsigned integer type.
- [u32]() 	    The 32-bit unsigned integer type.
- [u64]() 	    The 64-bit unsigned integer type.
- [u128]() 	    The 128-bit unsigned integer type.
- [unit]()        The () type, sometimes called "unit" or "nil".
- [usize]()       The pointer-sized unsigned integer type.
- [never]() 	    [Experimental]The ! type, also called "never".

### 模块

- [alloc]() Memory allocation APIs
- [any]() This module implements the Any trait, which enables dynamic typing of any 'static type through runtime reflection.
- [arch]() SIMD and vendor intrinsics module.
- [ascii]()  Operations on ASCII strings and characters.
- [borrow]() A module for working with borrowed data.
- [boxed]() A pointer type for heap allocation.
- [cell]() Shareable mutable containers.
- [char]() A character type.
- [clone]() 	The Clone trait for types that cannot be 'implicitly copied'.
- [cmp]() 	Functionality for ordering and comparison.
- [collections]() 	Collection types.
- [convert]() 	Traits for conversions between types.
- [default]() 	The Default trait for types which may have meaningful default values.
- [env]() 	Inspection and manipulation of the process's environment.
- [error]() 	Traits for working with Errors.
- [f32]() 	This module provides constants which are specific to the implementation of the f32 floating point data type.
- [f64]() 	This module provides constants which are specific to the implementation of the f64 floating point data type.
- [ffi]() 	Utilities related to FFI bindings.
- [fmt]() 	Utilities for formatting and printing Strings.
- [fs]() 	Filesystem manipulation operations.
- [hash]() 	Generic hashing support.
- [hint]() 	Hints to compiler that affects how code should be emitted or optimized.
- [i8]() 	The 8-bit signed integer type.
- [i16]() 	The 16-bit signed integer type.
- [i32]() 	The 32-bit signed integer type.
- [i64]() 	The 64-bit signed integer type.
- [i128]() 	The 128-bit signed integer type.
- [io]() 	Traits, helpers, and type definitions for core I/O functionality.
- [isize]() 	The pointer-sized signed integer type.
- [iter]() 	Composable external iteration.
- [marker]() 	Primitive traits and types representing basic properties of types.
- [mem]() 	Basic functions for dealing with memory.
- [net]() 	Networking primitives for TCP/UDP communication.
- [num]() 	Additional functionality for numerics.
- [ops]() 	Overloadable operators.
- [option]() 	Optional values.
- [os]() 	OS-specific functionality.
- [panic]() Panic support in the standard library.
- [path]() Cross-platform path manipulation.
- [prelude]() 	The Rust Prelude.
- [process]() 	A module for working with processes.
- [ptr]() 	Manually manage memory through raw pointers.
- [rc]() 	Single-threaded reference-counting pointers. 'Rc' stands for 'Reference Counted'.
- [result]() 	Error handling with the Result type.
- [slice]() 	A dynamically-sized view into a contiguous sequence, [T].
- [str]() 	Unicode string slices.
- [string]() 	A UTF-8 encoded, growable string.
- [sync]() 	Useful synchronization primitives.
- [thread]() 	Native threads.
- [time]() 	Temporal quantification.
- [u8]() 	The 8-bit unsigned integer type.
- [u16]() 	The 16-bit unsigned integer type.
- [u32]() 	The 32-bit unsigned integer type.
- [u64]() 	The 64-bit unsigned integer type.
- [u128]() 	The 128-bit unsigned integer type.
- [usize]() 	The pointer-sized unsigned integer type.
- [vec]() 	A contiguous growable array type with heap-allocated contents, written Vec<T>.
- [future]() 	[Experimental] Asynchronous values.
- [intrinsics]() 	[Experimental]rustc compiler intrinsics.
- [pin]() 	[Experimental]Types which pin data to its location in memory
- [raw]() 	[Experimental]Contains struct definitions for the layout of compiler built-in types.
- [task]() 	[Experimental]Types and Traits for working with asynchronous tasks.

### 宏

- [assert]()	Ensure that a boolean expression is true at runtime.
- [assert_eq]()	Asserts that two expressions are equal to each other (using PartialEq).
- [assert_ne]()	Asserts that two expressions are not equal to each other (using PartialEq).
- [cfg]()	Boolean evaluation of configuration flags, at compile-time.
- [column]()	A macro which expands to the column number on which it was invoked.
- [compile_error]()	Unconditionally causes compilation to fail with the given error message when encountered.
- [concat]()	Concatenates literals into a static string slice.
- [debug_assert]()	Ensure that a boolean expression is true at runtime.
- [debug_assert_eq]()	Asserts that two expressions are equal to each other.
- [debug_assert_ne]()	Asserts that two expressions are not equal to each other.
- [env]()	Inspect an environment variable at compile time.
- [eprint]()	Macro for printing to the standard error.
- [eprintln]()	Macro for printing to the standard error, with a newline.
- [file]()	A macro which expands to the file name from which it was invoked.
- [format]()	Creates a String using interpolation of runtime expressions.
- [format_args]()	The core macro for formatted string creation & output.
- [include]()	Parse a file as an expression or an item according to the context.
- [include_bytes]()	Includes a file as a reference to a byte array.
- [include_str]()	Includes a utf8-encoded file as a string.
- [is_x86_feature_detected]()	A macro to test at runtime whether a CPU feature is available on x86/x86-64 platforms.
- [line	A macro]() which expands to the line number on which it was invoked.
- [module_path]()	Expands to a string that represents the current module path.
- [option_env]()	Optionally inspect an environment variable at compile time.
- [panic]()	The entry point for panic of Rust threads.
- [print]()	Macro for printing to the standard output.
- [println]()	Macro for printing to the standard output, with a newline.
- [stringify]()	A macro which stringifies its arguments.
- [thread_local]()	Declare a new thread local storage key of type std::thread::LocalKey.
- [try]()	Helper macro for reducing boilerplate code for matching Result together with converting downstream errors.
- [unimplemented]()	A standardized placeholder for marking unfinished code.
- [unreachable]()	A utility macro for indicating unreachable code.
- [vec]()	Creates a Vec containing the arguments.
- [write]()	Write formatted data into a buffer.
- [writeln]()	Write formatted data into a buffer, with a newline appended.
- [await]()	[Experimental]
- [concat_idents]()	[Experimental] Concatenate identifiers into one identifier.
- [dbg]()	[Experimental] A macro for quick and dirty debugging with which you can inspect the value of a given expression. An example:
- [is_aarch64_feature_detected]()	[Experimental]
- [is_arm_feature_detected]()	[Experimental]
- [is_mips64_feature_detected]()	[Experimental]
- [is_mips_feature_detected]()	[Experimental]
- [is_powerpc64_feature_detected]()	[Experimental]
- [is_powerpc_feature_detected]()	[Experimental]
- [select]()	[Experimental] A macro to select an event from a number of receivers.

### 关键字
