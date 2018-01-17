#### 怎么新建一个控制器

在Http/Controllers目录下新建php文件。

控制器在项目的app/Http/Controllers目录下

* 控制器的命名空间要和遵循php5规范，和目录一致，所以命名空间是namespace App\Http\Controllers;
* 命名一个新的类，命名和文件名一直，并继承自控制器基类Controllers
* 在类中新建方法。

#### 控制器和路由怎么进行关联

* 在路由中新建相应的路由，Route::get\("http子路径", “控制器类名@类中方法名”\);  就关联了路由和控制器。或者使用Route::get\("http子路径", \['use“ =&gt; '控制器类名@类中方法名” , 'as' =&gt; '路由别名'\);  进行关联。



#### 关联控制器后，路由的特性怎么用

传参数

过滤





