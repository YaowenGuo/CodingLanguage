laravel 中提供了DB facade(原始查找)，查询构造器 和 Eloquent ORM三种数据库操作方式。

#### 链接数据库

数据表创建好之后，首先要链接数据库。在database.php中发现，有如下的操作：
```php
'mysql' => [
            'driver' => 'mysql',
            'host' => env('DB_HOST', '127.0.0.1'),
            'port' => env('DB_PORT', '3306'),
            'database' => env('DB_DATABASE', 'forge'),
            'username' => env('DB_USERNAME', 'forge'),
            'password' => env('DB_PASSWORD', ''),
            'unix_socket' => env('DB_SOCKET', ''),
            'charset' => 'utf8mb4',
            'collation' => 'utf8mb4_unicode_ci',
            'prefix' => '',
            'strict' => true,
            'engine' => null,
        ],

```
这就是获取数据库相关配置的地方，而数据库的配置就在.env文件中，修改相应的变量即可。
```php
DB_CONNECTION=mysql
DB_HOST=192.168.8.152
DB_PORT=3307
DB_DATABASE=panda_site
DB_USERNAME=root
DB_PASSWORD=root

```
可以看到，两边是一一对应的。

#### 使用DB facade 执行sql指令。

可以在Controlor的方法中直接执行SQL语句
```php
public function test() {
    $testSql = DB::select('select * from student');
    return var_dump($testSql);
}
```
插入
$boolValue = DB::insert('insert into student(name, age) values (?, ?)', ['sao', 14]);

修改
DB::update('update student set age = ? where name = ?', [20, 'sao']); 返回修改的行数。