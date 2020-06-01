### 练习debug
#### 配置debug环境（XAMPP（PHP)+xdebug)
#### 方法：
#### 1.安装xdebug：先查看自己的D盘中,php\ext中有没有php_xdebug.dll，如果没有，可以在网站上（https://xdebug.org/download/historical）搜索自己所对应的xdebug的版本，
#### 2.修改php.ini
php.ini原来内容：zend_extension="/usr/local/php/ext/php_xdebug.dll"
;xdebug.profiler_append = 0
;xdebug.profiler_enable = 1
;xdebug.remote_port=9000
;xdebug.idekey=PHPSTORM
;xdebug.profiler_enable_trigger = 0
;xdebug.profiler_output_dir = "D:\must\tmp"
;xdebug.profiler_output_name = "cachegrind.out.%t-%s"
;xdebug.remote_enable = true
;xdebug.remote_handler = "dbgp"
;xdebug.remote_host = "127.0.0.1"
;xdebug.trace_output_dir = "D:\must\tmp"
修改后：（全部注释掉，填好xdbug.dll所在的完全地址）
zend_extension="D:\must\php\ext\php_xdebug.dll"
xdebug.profiler_append = 0
xdebug.profiler_enable = 1
xdebug.remote_port=9000
xdebug.idekey=PHPSTORM
xdebug.profiler_enable_trigger = 0
xdebug.profiler_output_dir = "D:\must\tmp"
xdebug.profiler_output_name = "cachegrind.out.%t-%s"
xdebug.remote_enable = 1
xdebug.remote_handler = "dbgp"
xdebug.remote_host = "127.0.0.1"
xdebug.trace_output_dir = "D:\must\tmp"
#### 3.重启apache,查看phpinfo,如果有Xdebug显示，则成功拥有了xdebug
成功页面如下：
