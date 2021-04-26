# C/C++ 宏

显示编译器预定义的宏

https://blog.kowalczyk.info/article/j/guide-to-predefined-macros-in-c-compilers-gcc-clang-msvc-etc..html

```
touch 1.h
gcc -E -dM 1.h
```

编译器参数指定宏 `-D<Macro<=Value>>`

例如
```
# cat test.c
char* str = macro;

# clang -Dmacro=\"aaa\" -E -c test.c
# 1 "text.c"
# 1 "<built-in>" 1
# 1 "<built-in>" 3
# 366 "<built-in>" 3
# 1 "<command line>" 1
# 1 "<built-in>" 2
# 1 "text.c" 2
char* str = "aaa";
```

`-E` 表示只进行预处理，不编译。可以看到 `-D` 指定的宏已经被替换为了其值。


**宏可以有值，也可以没有值**


