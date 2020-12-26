# Ownership

堆内存的管理一直是内存管理的一个难题，目前处理堆内存管理主要有两种方式：

- 开发者自己管理堆的申请和释放。C，C++ 都是需要开发者来处理。这种方式主要的问题是，开发很可能忘记释放内存，在逻辑复杂的情况下，很可能很难判断什么时候该释放。

- 有垃圾回收器定期回收。垃圾回收器由独立的内存管理进程，定期回收不再使用的堆空间。垃圾回收器的问题是，因为牵涉到现有变量内存的整理和变量指向修改。垃圾回收会暂停程序的执行，而且时间是不可预测的。这对于实时系统是不可接受的。


Rust 才用了一中独特的方式，有编译器来推测并释放对空间。没有垃圾回收的耗时，拥有和开发者自主管理释放堆一样的效率。同时由于有编译器的来管理释放，开发者不再费劲心力关于堆空间的释放。而且由于编译器的强制检查，不会存在被忘记释放的内存。

为了实现编译器的推测，Rust 引入了所有权和生命周期的概念。

## 所有权规则

- 每个值都有一个变量，被称为所有者。
- 在同一时刻仅能有一个所有者。
- 当所有者出来自己的作用域之后，该值被删除。

变量复制、函数参数传递、返回值都会转移所有权。

When a variable goes out of scope, Rust calls a special function for us. This function is called drop

When a variable that includes data on the heap goes out of scope, the value will be cleaned up by drop unless the data has been moved to be owned by another variable.


哪些类型是复制的？

- All the integer types, such as u32.
- The Boolean type, bool, with values true and false.
- All the floating point types, such as f64.
- The character type, char.
- Tuples, if they only contain types that are also Copy. For example, (i32, i32) is Copy, but (i32, String) is not.
- A type has the Copy trait, an older variable is still usable after assignment. Rust won’t let us annotate a type with the Copy trait if the type, or any of its parts, has implemented the Drop trait. 

通常，任何一组简单标量值可能是复制的。任何部分不需要申请资源的是复制的。 For example, (i32, i32) is Copy, but (i32, String) is not.

