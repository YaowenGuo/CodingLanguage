## Blade 模板引擎简介及模板继承的使用
- Blade 是 Laravel 提供的一个简单但是功能强大的引擎。
- 和其他流行的php模板引擎不一样，blade并不限制你在模板中使用原生php代码。
- 所有Blade视图页面都将被编译成原生的php代码并缓存起来，除非模板文件改变了，否则不会重新编译。

在view下新建根 view 布局文件后缀是.blade.php。

在该模板中编写html代码，使用
```
@section(“片段名称”)
临时内容
@show
```
在模板中预留一个位置，为讲台被其他页面修改的位置。

要实现模板时，只需要在子页面中写继承自哪个模板
```
@entends（‘layout.main') # 继承自 view/layout/main.blade.php

# 饭后重写
@section('模板中的section名')
# 要代替的内容
# 如果要连模板中的内容一起输出，添加
    @parent
    
@endsection

```

预留位置除了@section之外，还可以使用@yield('名字') 。@yield只能定义一个位置，不能自己附带内容。

```
@yield('名字')
```
重写@yield('名字')跟重写@section一样，都使用@section ... @endsection

标签。

## 基础语法和include的使用

## 流程控制

## 模板中的URL

