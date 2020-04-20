##### 考虑一个熟人表acquaintance (friend1, friend2, class)，表示friend1和friend2是朋友，class表示类别，比如“书友”，“球友”，“酒友”等等。  

###### 1.定义acquaintance表  
-- 在MySQL数据库新建此表 ，该表的定义语句:  
 create table acquaintance ( friend1 varchar(10), friend2 varchar(10), class varchar(10) );

###### 2.利用ODBC和datafactory建立测试数据的步骤如下： 
原理：通过和数据库进行连接后，对选定表的字段设定一定的插入规则，然后批量插入记录。Datafactory支持各种主流数据库（Oracle、DB2、MS SQL），甚至excel、access等。  
下载DataFactory并进行安装，下载地址：链接：https://pan.baidu.com/share/init?surl=0PiqHxa4CpCUKaqAb-n99w 提取码：wq47 。  
下载MySQL-ODBC驱动并安装，下载安装myodbc32驱动 ： https://dev.mysql.com/downloads/connector/odbc/。  
a. 启动DataFactory，通过ODBC连接MySQL数据库  
b. 选择DBC Administrator对ODBC用户DSN的配置  
c. 进入ODBC数据源管理器，通过点击“添加”来新增用户数据源  
d. 配置MySQL连接信息（DataSourceName:localhost/user:root/database:） 
e. 配置好数据源后返回到步骤b的页面，此时需要选择数据源，由于新建的数据源此时还无法进行选择，因此取消此安装流程，重新打开一个新的连接流程即可  
f. 选择相应数据表  
g. 选择acquaintance,并进入下一步，指定执行名称为：add_acquaintance  
h. 完成配置，如图：

-- 开始随机生成数据：
将friednd1设置成长度为1-10的随机字符串  
将friednd2设置成长度为1-10的随机字符串  
将class设置成长度为1-5的随机字符串  
结果：重新通过可视化工具查看，发现数据已经成功生成，如图：

笔记参考：https://blog.csdn.net/u014553029/article/details/89433709
