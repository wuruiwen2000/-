### 题目：基于PHP的CMS系统的安装配置与测试，并在本地配置虚拟域名进行访问
#### 基于php的CMS系统drupal的安装：
##### requirements：xampp（注意其中的php等的version要与drupal相匹配，可以查看网站中的requirements for drupal installation)
- 安装xampp，启动apache和mysql。注意：80端口和3306端口不能给其它程序占用。
- 根据电脑的xampp中php等的版本，去https://www.drupal.org/下载合适版本，windows系统下载zip版本。把下载drupal版本解压。（本次下载的是drupal7.6.2)
- 把drupal版本解压文件夹复制到安装xampp文件夹下htdocs。
- 打开xampp软件下mysql管理页面(phpmyadmin)，按admin就ok。
- 建立一个drupal8数据库，点击"数据库"，在新建数据库填好名称，排序规则选择utf8_general_ci，最后按建立。
- 为刚才建立的数据库增加一个用户，点击新建，再按权限就出现新增用户账户。填写新增用户账户内容，自已建个新用户不能用root，admin，administrator，服务器名称用本地就可以，设置一个密码，一定要全局权限打上对，最后执行就可以。
打开浏览器输入安装路径：localhost/drupal（版本）/index.php就会出现安装界面。
- 依次按照要求填好信息:输入之前建立的MySQL数据库资料（数据库的名字、用户名、密码、端口数等等）->填要使用的网站的信息（网站名、邮箱名、网站用户名、网站用户密码等等）
- 最后完成。
