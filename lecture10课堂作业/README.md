### 1.php程序的运行流程
#### PHP代码被PHP解释器解释后可运行于服务器上的Web端。web端的运行机制是HTTP。HTTP是一种基于Request/Response的协议，是支持Web运行的协议基础。HTTP的客户端发送Request到服务器端，服务器端返回Response。Request中包含客户端需要访问的页面的文件名。服务器端返回该文件名指向的网页。如果没有使用PHP、JavaScript等，HTTP协议传输只能是静态的HTML文件。也就是，HTML文件不会受到用户行为的影响，内容一直保持不变。如果要实现动态网页，就需要使用PHP或JavaScript。PHP是用于服务器端的编程语言，JavaScript是多用于客户端的编程语言。
#### PHP代码是在服务器端被执行的。当用户访问一个包含PHP的网页时，发送Request到服务器，其中包含网页的文件名。服务器收到Request后，找到文件名指向的文件，发现其中嵌有PHP代码，会调用PHP解释器处理该文件，然后将处理后的结果整理到Response，发送到客户端。PHP代码可以与服务器端的数据库或其他资源进行交互，或者根据用户的操作产生不同的页面。
#### 因此，PHP脚本的触发是在服务器收到客户端的Request。收到一个Request后，服务器触发一个PHP脚本；处理完脚本后，返回结果到客户端，等待下一个Request。当收到下一个Request后，服务器触发另一个（或同一个）PHP脚本。两次PHP脚本的运行是相互独立的，第二次脚本的运行几乎不受前一次脚本运行的影响。
#### PHP的代码块PHP代码是可以嵌入到HTML文件中的，经常可以在HTML文件中看到散落在各处的PHP代码块。PHP是会忽略两个PHP代码块之间HTML代码的自动执行。
### 2.目前常用的服务器软件有哪些
#### 服务器和本地PC差不多，根据需要可以安装需要的软件，主要功能是各种提供网络服务。
#### 在网络环境下，根据服务器提供的服务类型不同，分为文件服务器，数据库服务器，应用程序服务器，web服务器等。
#### 常用的有：
#### 文件服务器主要有ftp和NFS,ftp服务的有：Serv-U、FileZilla 等，
#### 数据库服务的MySQL，oracle，sqlserver等，
#### 服务器程序语言：php、ASP、.net等软件等，
#### 提供web服务的IIS，Apache，Tomcat，GFE,Nginx等(https://www.idc889.com/detail-2886.html)。
### 3.如何将php与Apache建立关联
#### 配置apache使其关联php：
- 打开Conf/httpd.conf，找到 ServerRoot （或者Define SRVROOT），将其指向你apache的路径，例 ： Define SRVROOT D:\apache
- 找到ServerAdmin 改为 localhost，访问localhost 成功即为安装成功
- 尾部加入LoadModule php5_module "D:\php5.6\php5apache2_4.dll"  //PHP 文件所在路径
AddType application/x-httpd-php .php .html .htm
最后在Apache   \htdocs 下创建index.php 输出phpinfo 
- 启动Apache，访问localhost，查看是否安装成功
### 4.主目录下面的子目录和虚拟目录有何不同：
#### 很多时候，上传百的文件多了，架设服务器当初设定的主目录所在盘空间往往就不够了，这就需要设置虚拟目录。
#### 虚拟目录就是将其他目录以映射的方式虚拟到该FTP服务器的主目录下，一个FTP服务器的主目录道实质上就可以包括很多不同盘符、不同路径的目录，而不会受到所在盘空间的限制了。
#### 当用户登录到主目录下，还可以根据该账户的权限对它进行相应的操作，就像操作主目录下的子目录一样。
