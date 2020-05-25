### 查看自己的服务器程序的配置文件
查看apache的配置文件：点开xampp，打开apache后点config,就出现了apache的配置文件
### 阅读配置文件中的注释，了解种配置的基本信息
#### Apache主配置文件注释(apache的主配置文件为：httpd.conf（This is the main Apache HTTP server configuration file）)
【主要信息】
- 配置位置：/apache/cong/httpd.conf

- 文档根目录：ServerRoot "D:/must/apache"
用于指定Apache的运行目录，服务启动之后自动将目录改变为当前目录，在后面使用到的所有相对路径都是相对这个目录下
部分如下：
（#
DocumentRoot: The directory out of which you will serve your
documents. By default, all requests are taken from this directory, but
symbolic links and aliases may be used to point to other locations.
#）

- 端口号：Listen 80
监听的端口，如有多块网卡，默认监听所有网卡

- 相对路径别名：Alias /icons/ "/var/www/icons/"   
#定义一些不在DocumentRoot下的文件，而可以将其映射到网页根目录中，这也是访问其他目录的一种方法，但在声明的时候切记目录后面加”/”

- vhost：httpd-vhosts.conf虚拟主机配置文件注释  
[root@extra]# egrep -v "^.*#|^$" httpd-vhosts.conf |nl  
     1  NameVirtualHost *:80                                # 基于名称的虚拟主机配置（ *:80表示监听本机所有ip）  
     2  <VirtualHost *:80>                                  # 定义一个虚拟主机  
     3      ServerAdmin webmaster@dummy-host.example.com    # 配置管理员邮箱  
     4      DocumentRoot "/application/apache2.2.22/docs/dummy-host.example.com"  # 程序的站点目录  
     5      ServerName dummy-host.example.com               # 域名服务，需要apache mode_alias模块支持  
     6      ServerAlias www.dummy-host.example.com          # 虚拟主机别名  
     7      ErrorLog "logs/dummy-host.example.com-error_log"# 错误的日志路径  
     8      CustomLog "logs/dummy-host.example.com-access_log" common  #访问日志配置（生产环境我们用combined格式代替common格式）  
     9  </VirtualHost>  
    10  <VirtualHost *:80>  
    11      ServerAdmin webmaster@dummy-host2.example.com  
    12      DocumentRoot "/application/apache2.2.22/docs/dummy-host2.example.com"  
    13      ServerName dummy-host2.example.com  
    14      ErrorLog "logs/dummy-host2.example.com-error_log"  
    15      CustomLog "logs/dummy-host2.example.com-access_log" common  
    16  </VirtualHost>  
【其他信息】
- UseCanonicalName Off
如果客户端提供了主机名和端口，Apache将会使用客户端提供的这些信息来构建自引用URL。这些值与用于实现基于域名的虚拟主机的值相同，并且对于同样的客户端可用。
（关于目录）

- DocumentRoot "/var/www/html"    # apache的默认web站点目录路径，结尾不要添加斜线


### 对比自己的服务器配置和课件中配置说明
对比后，主要的不同在于主要是修改了对alias的配置和对根目录的配置，修改后使用起来更加方便  
alias配置总结：  
第一部分是Alias，表示别名的意思，是个关键词。  
第二部分是/color，表示你将来要通过http://{你服务器的地址}/color来访问到你自己的东西。  
第三部分是/usr/html/color，表示你上传项目的路径，放在这里。  
默认根目录配置总结：  
将以下的代码修改为如下图：
![image](https://github.com/wuruiwen2000/-/blob/master/lecture11%E8%AF%BE%E5%A0%82%E4%BD%9C%E4%B8%9A/%E6%A0%B9%E7%9B%AE%E5%BD%95%E9%85%8D%E7%BD%AE.PNG)
