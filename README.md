# rust-std

Rust 标准库中文翻译。欢迎大家参与进来，也欢迎大家加入 **RCTT** (Rust Chinese Translation Team)，在本仓库提交 issue 即可，我会及时主动邀请你。

QQ交流群：962057386

---

## 相关

更多请看 (Rust 标准库官方文档)[https://doc.rust-lang.org/std/]，鉴于译者水平有限，如有疑问欢迎提出^_^ 。

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

### 模块


### 宏

### 关键字
