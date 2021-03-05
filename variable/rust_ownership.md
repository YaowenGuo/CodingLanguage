# 变量

## 变量

1. 使用 `let` 声明变量，使用 `mut` 修饰可变变量。默认是不可变的。

```rust
let foo = 5; // immutable
let mut bar = 5; // mutable
```

2. Rust 变量不允许有 null 值，在使用之前必须复制，否则报错。

```
let a;

{
    // print!("value of a: {}", a); // 无法通过，不能有空值
    a = 123;
    print!("value of a: {}", a);
}
```

3. 如果变量的类型可以推断，则不用指明类型，否者需要再变量后用冒号 `:` 分割类型。

```rust
let a: i32;
```

4. rust 是强类型语言，一但变量类型确定，就不能改变。

```

```

5. 使用 const 声明常量，并且必须声明类型。

```rust
const MAX_POINTS: u32 = 100_000;
```
- const 总是不可变的，不能用 mut 修饰。

- const 可以声明在全局作用域中，而变量不可以。

- 最后一个区别是常量只能设置为常量表达式，而不能设置为函数调用的结果或只能在运行时计算的任何其他值。

7. 覆盖。跟其它语言不通，Rust 可以声明相同名字的变量，后声明的会覆盖之前的。甚至可以类型不同。

```rust
let mut i = 1;
printin!("i value is: {}", i);
let i = "hello";
println!("i value is: {}", i);
```



## 引用




## Ownership

堆空间的内存管理一直是个难题，有些语言要求编程人员自己管理堆空间（C/C++），有些语言使用垃圾回收器管理不再使用的堆。Rust 则使用所有权系统和一些列规则，在编译期检查。所有的所有权均不会在运行时降低程序的运行速度。

所有权要解决的问题：

1. 跟踪代码和堆上数据的关系。
2. 管理堆上大量的重复数据。
3. 清理不再使用的数据，从而避免内堆空间用完。

熟悉所有权的存在是为了管理堆数据可以帮助理解它的工作方式。


### 所有权规则

- Rust中的每个值都有一个变量，称为其所有者。

- 同一时刻只能有一个所有者。(标量由于是值拷贝，因此同一时刻也仅有一个所有者。)

- 当所有者超出作用域后，值就会被删除。


和其他语言一样，Rust 的简单数据类型是值拷贝，而复杂数据类型是引用拷贝。因此会出现

例如

```Rust
let a = 3;
let b = a;
println!("Is a available: {}, {}", a, b);

let s = String::from("hello world!");
let s1 = s;
// Will not working.
println!("{}, {}", s, s1); 

```


**复合类型的变量，函数参数同样会传递所有权。返回值也可以传递所有权。**


```rust
fn main() {
    let s = String::from("hello");  // s comes into scope

    takes_ownership(s);             // s's value moves into the function...
                                    // ... and so is no longer valid here

    let s1 = gives_ownership(); // s1 可用。

} // Here, x goes out of scope, then s. But because s's value was moved, nothing
  // special happens.

fn takes_ownership(some_string: String) { // some_string comes into scope
    println!("{}", some_string);
} // Here, some_string goes out of scope and `drop` is called. The backing
  // memory is freed.


fn gives_ownership() -> String {             // gives_ownership will move its
                                             // return value into the function
                                             // that calls it

    let some_string = String::from("hello"); // some_string comes into scope

    some_string                              // some_string is returned and
                                             // moves out to the calling
                                             // function
}

```

### 作用域

一个花括号是一个作用域，在作用域内声明的变量，草除作用域后会失效。

```rust
{                      // s is not valid here, it’s not yet declared
    let s = "hello";   // s is valid from this point forward

    // do stuff with s
}                      // this scope is now over, and s is no longer valid
```

### 引用和租借

