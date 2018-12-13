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


### 宏

### 关键字
