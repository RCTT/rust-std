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
- [ops]() 	可重载的操作符。
- [option]()  可选的值。
- [os]() 	操作系统相关的基础功能。
- [panic]() 标准库中panic的支持模块。
- [path]() 跨平台的路径操作模块。
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

- [assert]()	该宏确保布尔表达式在运行期始终为true。
- [assert_eq]()	该宏判断两个表达式求值后是否相等 (使用 PartialEq 特性)。
- [assert_ne]()	该宏判断两个表达式求值后是否不相等 (使用 PartialEq 特性)。
- [cfg]()	在编译时期，该宏将配置标记进行布尔表达式求值的宏。
- [column]()	该宏返回当前程序所在的代码行号。
- [compile_error]()	该宏可以在编译时，无条件的导致一个编译错误，并报告其所携带的错误信息。
- [concat]()	该宏将多个字面量值链接成为一个静态的字符串切片。
- [dbg]() 一个用于快速debug，方便检查一个表达式值的宏。
- [debug_assert]()	该宏确保布尔表达式在运行期始终为true。
- [debug_assert_eq]()	该宏判断两个表达式求值后是否相等。
- [debug_assert_ne]()	该宏判断两个表达式求值后是否不相等。
- [env]()	该宏在编译期检查并返回一个环境变量值。
- [eprint]()	使用此宏可以在标准错误输出中打印信息。
- [eprintln]()	使用此宏可以在标准错误输出中打印信息,并在末尾加上 `\newline`。
- [file]()	该宏可以返回当前执行函数所在的文件的文件名。
- [format]()	该宏使用运行期插入的表达式返回一个字符串。
- [format_args]()	该宏用于创建或者输出一个格式化后的字符串。
- [include]()	该宏将一个文件的内容解析并引入到当前的运行上下文中。
- [include_bytes]()	以byte数组的方式对文件进行解析，并实现include。
- [include_str]()	以UTF-8编码字符串的方式对文件进行解析，并实现include。
- [is_x86_feature_detected]()	该宏用于测试一个cpu 特性是否可以用于 x86/x86-64 指令集平台。
- [line]() which 该宏可以返回当前执行程序所在的代码行的行号。
- [module_path]()	该宏返回当前文件所在的模块路径。
- [option_env]()	该宏在编译期，检查一个宏，并返回使用 `Option` 类型包装的环境变量值。
- [panic]()	该宏可以在一个Rust线程内引起线程恐慌。
- [print]()	该宏用于将内容打印到标准输出中。
- [println]()	该宏用于将内容打印到标准输出中，并在末尾加上 `\newline`。
- [stringify]()	该宏可以将他的参数字符串化后返回。
- [thread_local]()	Declare a new thread local storage key of type std::thread::LocalKey.
- [try]()	Helper macro for reducing boilerplate code for matching Result together with converting downstream errors.
- [unimplemented]()	标记未完成代码的占位宏。
- [unreachable]()	表明不可达代码的通用宏。
- [vec]()	使用参数构建Vec的宏。
- [write]()	使用该宏可以将格式化的数据写入一个buffer中。
- [writeln]()	使用该宏可以将格式化的数据写入到一个buffer中，并在末尾加上 `\newline`
- [await]()	[实验性] 一个用于等待异步调用返回的宏。
- [concat_idents]()	[实验性] 该宏将多个标识符链接成为一个标识符号。
- [is_aarch64_feature_detected]()	[实验性] Prevents compilation if is_aarch64_feature_detected is used somewhere else than aarch64 targets.
- [is_arm_feature_detected]()	[实验性] Prevents compilation if is_arm_feature_detected is used somewhere else than ARM targets.
- [is_mips64_feature_detected]()	[实验性] Prevents compilation if is_mips64_feature_detected is used somewhere else than MIPS64 targets.
- [is_mips_feature_detected]()	[实验性] Prevents compilation if is_mips_feature_detected is used somewhere else than MIPS targets.
- [is_powerpc64_feature_detected]()	[实验性] Prevents compilation if is_powerpc64_feature_detected is used somewhere else than PowerPC64 targets.
- [is_powerpc_feature_detected]()	[实验性] Prevents compilation if is_powerpc_feature_detected is used somewhere else than PowerPC targets.
- [select]()	[废弃的] [实验性] 该宏用于在一系列事件接受者中选取一个处理当前时间。

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