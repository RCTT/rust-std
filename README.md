# rust-std

Rust 标准库中文翻译。欢迎大家参与进来，也欢迎大家加入 **RCTT** (Rust Chinese Translation Team)，在本仓库提交 issue 即可，我会及时主动邀请你。

QQ交流群：962057386

---

## 相关

更多请看 [Rust 标准库官方文档](https://doc.rust-lang.org/std/)，鉴于译者水平有限，如有疑问欢迎提出^_^ 。

## rust 标准库教程

本文档致力于指出Rust标准库的显著特性。

### 容器与集合类型


- [Vec<T>]() - 在堆上分配，运行期间可调整大小的 vector。
- [[T; n]]() - 在编译时具有固定大小的内联数组。
- [[T]]() - 一个动态大小的切片，它可以被分配到任何不同类型的连续存储中，不管是不是在堆上堆分配。

切片只能通过某种类型的指针来处理，因此有很多类型，例如:

- [&[T]]() - 切片引用
- [&mut [T]]() - 可变切片
- [Box<[T]>]() - 拥有的切片

### 基本类型

- [array]()	   一个固定大小的数组, 写作 [T; N]，表示元素类型 T 和非负编译时常数大小 N。
- [bool]() 	    布尔类型。
- [char]() 	    字符类型。
- [f32]() 	    32 位浮点数。
- [f64]()     	64 位浮点数。
- [fn]()      	函数指针, 形如 `fn(usize) -> bool`。
- [i8]() 	    8 位有符号整形。
- [i16]() 	    16 位有符号整形。
- [i32]()     	32 位有符号整形。
- [i64]()     	64 位有符号整形。
- [i128]()    	128 位有符号整形。
- [isize]()       指针大小的有符号整数类型。
- [pointer]() 	裸指针，不安全指针, *const T 和 *mut T.
- [reference]()   引用，包括共享的和可变的。
- [slice]() 连续序列的动态大小视图[T]。
- [str]() 	   字符串切片。
- [tuple]()       有限非均匀序列（元组）, (T, U, ..)。
- [u8]() 	    8 位无符号整形。
- [u16]() 	    16 位无符号整形。
- [u32]() 	    32 位无符号整形。
- [u64]() 	    64 位无符号整形。
- [u128]() 	    128 位无符号整形。
- [unit]()      () 类型,称作 "unit" 或者 "nil".
- [usize]()       指针大小的无符号整数类型。
- [never]() 	    [Experimental] `!` 类型, 也称作 "never".

### 模块

- [alloc]() 内存分配API。
- [any]() 这个模块实现了`Any trait`，它通过运行时反射支持任何静态类型的动态类型。
- [arch]() SIMD 和 vendor 内部特性模块。
- [ascii]()  ASCII 字符串与字符的相关操作符。
- [borrow]() 处理借用数据的模块。
- [boxed]() 在堆上分配的一种指针类型。
- [cell]() 可共享的可变容器。
- [char]() 字符类型。
- [clone]() 无法“隐式复制”类型的 `clone` trait。
- [cmp]() 	排序和比较。
- [collections]() 	集合类型。
- [convert]() 	类型之间转换的特性。
- [default]() 可能有意义的默认值的类型的默认特性。
- [env]() 	检查和操作当前进程的环境变量。
- [error]() 	用于和错误打交道的特性。
- [f32]() 	这个模块提供了 `f32` 浮点数类型特有的常量。
- [f64]() 	这个模块提供了 `f64` 浮点数类型特有的常量。
- [ffi]() 	与FFI绑定有关实用工具。
- [fmt]() 	与格式化和打印字符串有关的实用工具。
- [fs]() 	文件系统相关操作。
- [hash]() 	泛化的HASH支持。
- [hint]() 	提示编译器如何触发或者优化代码的影响。
- [i8]() 	8位有符号整数类型。
- [i16]() 	16位有符号整数类型。
- [i32]() 	32位有符号整数类型。
- [i64]() 	64位有符号整数类型。
- [i128]() 	128位有符号整数类型。
- [io]() 	基础 I/O 功能 包括 特性， 帮助类， 和一些相关类型定义。
- [isize]() 	指针大小的有符号整数类型.
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
- [process]() 	一个用于处理进程的模块。
- [ptr]() 	通过裸指针管理内存。
- [rc]() 	在单线程中进行引用计数的指针类型。 'Rc' 表示 'Reference Counted'。
- [result]() 	提供在错误处理中使用Result类型的能力。
- [slice]() 	A dynamically-sized view into a contiguous sequence, [T].
- [str]() 	Unicode string slices.
- [string]() 	UTF-8编码可持续增长的字符串
- [sync]() 	一些有用的进行同步的基础功能。
- [thread]() 	系统原生线程管理。
- [time]() 	Temporal quantification.
- [u8]() 	8位无符号整数类型。
- [u16]() 	16位无符号整数类型。
- [u32]() 	32位无符号整数类型。
- [u64]() 	64位无符号整数类型。
- [u128]() 	128位无符号整数类型。
- [usize]() 	指针大小的无符号整数类型.
- [vec]() 	一种在堆上分配空间存储数据的，可持续增长的数组类型， 形如 Vec<T>。
- [future]() 	[实验性] Asynchronous values.
- [intrinsics]() 	[实验性]rustc compiler intrinsics.
- [pin]() 	[实验性]Types which pin data to its location in memory
- [raw]() 	[实验性]Contains struct definitions for the layout of compiler built-in types.
- [task]() 	[实验性]用于处理异步任务的一些类型和特性。

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
- [unimplemented]()	标记未完成代码的占位宏。
- [unreachable]()	表明不可达代码的通用宏。
- [vec]()	使用参数构建Vec的宏。
- [write]()	Write formatted data into a buffer.
- [writeln]()	Write formatted data into a buffer, with a newline appended.
- [await]()	[实验性]
- [concat_idents]()	[实验性] Concatenate identifiers into one identifier.
- [dbg]()	[实验性] A macro for quick and dirty debugging with which you can inspect the value of a given expression. An example:
- [is_aarch64_feature_detected]()	[实验性]
- [is_arm_feature_detected]()	[实验性]
- [is_mips64_feature_detected]()	[实验性]
- [is_mips_feature_detected]()	[实验性]
- [is_powerpc64_feature_detected]()	[实验性]
- [is_powerpc_feature_detected]()	[实验性]
- [select]()	[实验性] A macro to select an event from a number of receivers.

### 关键字

- [as]()	用于将一个值转换为类型的关键字。
- [const]()	用于定义常量。
- [crate]()	用于代码库的关键字。
- [enum]()	用于定义枚举。
- [extern]()	用于外部模块导入。
- [fn]()	用于定义函数。
- [for]()	for关键字。
- [if]()	if语句定义关键字。
- [impl]()	定义特性实现的关键字。
- [let]()	实现变量绑定的关键字。
- [loop]()	用于定义循环的关键字。
- [struct]()	用于定义结构体的关键字。