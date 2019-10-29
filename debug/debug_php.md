# PHP 安装

## MAC 环境安装

其实 MAC 已经自带了 php 和 apache，由于版本比较低，在安装新版本前，处于强迫症，你肯能想要卸载它。然而，有网友回答说，不建议卸载它，一是可能有一些软件依赖这些环境。二是，即使卸载了，它也会在系统升级是被从新安装。因此只需要另外安装一个 php 并配置用户下的环境变量即可。

使用 homwbrew 安装 php 

```
brew install php71
```

其实所有的配饰和使用 brew 都带有指导文档

```
brew info php71
```

它会列出配置环境和启动 php-fpm 的方法

```
Finally, check DirectoryIndex includes index.php
    DirectoryIndex index.php index.html

The php.ini and php-fpm.ini file can be found in:
    /usr/local/etc/php/7.1/

php@7.1 is keg-only, which means it was not symlinked into /usr/local,
because this is an alternate version of another formula.

If you need to have php@7.1 first in your PATH run:
  echo 'export PATH="/usr/local/opt/php@7.1/bin:$PATH"' >> ~/.zshrc
  echo 'export PATH="/usr/local/opt/php@7.1/sbin:$PATH"' >> ~/.zshrc

For compilers to find php@7.1 you may need to set:
  export LDFLAGS="-L/usr/local/opt/php@7.1/lib"
  export CPPFLAGS="-I/usr/local/opt/php@7.1/include"


To have launchd start php@7.1 now and restart at login:
  brew services start php@7.1
Or, if you don't want/need a background service you can just run:
  php-fpm
```

因此我们只需要将配置环境

```
echo 'export PATH="/usr/local/opt/php@7.1/bin:$PATH"' >> ~/.zshrc
echo 'export PATH="/usr/local/opt/php@7.1/sbin:$PATH"' >> ~/.zshrc
echo 'export LDFLAGS="-L/usr/local/opt/php@7.1/lib"' >> ~/.zshrc
echo 'export CPPFLAGS="-I/usr/local/opt/php@7.1/include"' >> ~/.zshrc

scource ~/.zshrc
```

这里需要注意你使用的 shell 是不是 zsh，如果不是可能需要输入到相应的配置文件。

然后根据需要启动 php-fpm

```
brew services start php@7.1

或者
php-fpm

```


安装 xdebug。 在启用了 `scource ~/.zshrc` 的终端，或者新启动的终端。 pecl 是默认可用的指令。可以用来安装对应版本的 xdebug

```
pecl install xdebug
```

在安装的输出信息里有要配置的信息， 例如，安装位置、配置过程和参考文档：


```
Libraries have been installed in:
   /private/tmp/pear/temp/pear-build-yaowenqtEx8b/xdebug-2.7.2/modules

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the `-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the `DYLD_LIBRARY_PATH' environment variable
     during execution

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------

Build complete.
Don't forget to run 'make test'.

running: make INSTALL_ROOT="/private/tmp/pear/temp/pear-build-yaowenqtEx8b/install-xdebug-2.7.2" install
Installing shared extensions:     /private/tmp/pear/temp/pear-build-yaowenqtEx8b/install-xdebug-2.7.2/usr/local/Cellar/php@7.1/7.1.32_1/pecl/20160303/

  +----------------------------------------------------------------------+
  |                                                                      |
  |   INSTALLATION INSTRUCTIONS                                          |
  |   =========================                                          |
  |                                                                      |
  |   See https://xdebug.org/install.php#configure-php for instructions  |
  |   on how to enable Xdebug for PHP.                                   |
  |                                                                      |
  |   Documentation is available online as well:                         |
  |   - A list of all settings:  https://xdebug.org/docs-settings.php    |
  |   - A list of all functions: https://xdebug.org/docs-functions.php   |
  |   - Profiling instructions:  https://xdebug.org/docs-profiling2.php  |
  |   - Remote debugging:        https://xdebug.org/docs-debugger.php    |
  |                                                                      |
  |                                                                      |
  |   NOTE: Please disregard the message                                 |
  |       You should add "extension=xdebug.so" to php.ini                |
  |   that is emitted by the PECL installer. This does not work for      |
  |   Xdebug.                                                            |
  |                                                                      |
  +----------------------------------------------------------------------+

...

Build process completed successfully
Installing '/usr/local/Cellar/php@7.1/7.1.32_1/pecl/20160303/xdebug.so'
install ok: channel://pecl.php.net/xdebug-2.7.2
Extension xdebug enabled in php.ini

```


下面就要按照上面 pecl 输出的内容配置了

1. 首先注释掉 php 默认的 zend_debug.

```
vim /usr/local/etc/php/7.1/php.ini

注释掉, 注意 php.ini 的注释号是分好 `;`

; zend_extension="xdebug.so"
```
如果有 `"extension=xdebug.so"` 也要注释掉。


2. 配置的 xdebug 的调试模块和端口：
由于默认的 php-fpm 的分布式部署已经占用了 9000 端口，我们需要修改 xdebug 的端口为其它闲置端口。 
由于 `/usr/local/etc/php/7.1/conf.d` 作为额外配置文件被导入，我们在这个目录下新建一个 `ext-xdebug.ini` 文件，添加配置：

```
[xdebug]
zend_extension="/usr/local/Cellar/php@7.1/7.1.32_1/pecl/20160303/xdebug.so"
xdebug.idekey = PHPSTORM
xdebug.remote_enable = On
xdebug.remote_host = "localhost"
xdebug.remote_connect_back=1
xdebug.remote_port = 9001
xdebug.handler = "dbgp"
xdebug.scream=0
xdebug.show_local_vars=1
```

然后重启 php-fpm 服务

```
brew services restart php71
```

然后查看配置是否生效

```
php -i | grep xdebug
```


3. 配置 PHPStom 

通过 pecl 安装的 xdebug 已经是和 PHP 版本匹配的，但是由于安装的 PHP 和 xdebug 可能比较新， PHPStorm 的版本比较旧的话，可能会出现问题，我就碰到了安装的 xdebug2.7.2 但是 PHPStorm 是 2017 版本，出现在 PHP 文件第一行断点，其后的断点不中断的现象，升级了 PHPStorm 就好了。按理说调试通过 `dbgp` 协议，协议应该兼容才对，但是既然有这个问题，请保证 PHPStorm 最新的来兼容 xdebug。



https://segmentfault.com/a/1190000011332021
https://www.jianshu.com/p/0dffa4a8eca2
https://www.jb51.net/article/155872.htm




关于配置的有几点要解释一下

> 配置 Brosser 插件和直接点 IDE 上的小虫子按钮在url 中添加参数的方式是一样的。只不过前者更适合一些异步请求的问题。


> 关于本机调试是否要开启远程调试？

本机调试其实没有必要配置远程配置，仅配置一个 


> remote_connect_back 和 remote_host

这两个配置项有紧密联系。

首先，如果你指针对单个调试用户，比如就你自己调试，你可以将remote_host设成你的Web程序运行的ip（比如本机，就设置为127.0.0.1），remote_connect_back的值不设置或者设置为0（你不设置默认也是0）。这样Xdebug每次调试的时候会固定连接remote_host指定的ip；
但是如果你支持的是多人调试，明显设置一个remote_host是没办法的。这个时候就可以用remote_connect_back=1来设置。当remote_connect_back设置为1的时候，xdebug会根据请求来的ip自动回连，进行调试，从而支持多人调试。同时，这个值设为1的话会使remote_host的设置无效；
一般情况下，推荐使用remote_connect_back=1的配置



如果有问题，可以根据这篇文章进行问题排查 https://blog.csdn.net/hfut_wowo/article/details/77488165


> 目录映射

在配置项目的目录映射时，如果是本地环境，按道理是不用映射的，但是我在本地的断点是无法停止的，所以配置了映射。需要注意的是，映射的目录是项目在你电脑上的绝对目录， 例如 `/User/xxx/php/web_magento_shopping_site`，而不是web 目录 `/`。远程调试也是项目在远程服务器的绝对目录。

