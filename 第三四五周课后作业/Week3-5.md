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
![image](https://github.com/wuruiwen2000/-/blob/master/%E7%AC%AC%E4%B8%89%E5%9B%9B%E4%BA%94%E5%91%A8%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/%E8%BF%90%E8%A1%8C%E7%BB%93%E6%9E%9C%E5%9B%BE1.png)

-- 开始随机生成数据：
将friednd1设置成长度为1-10的随机字符串  
将friednd2设置成长度为1-10的随机字符串  
将class设置成长度为1-5的随机字符串  
结果：重新通过可视化工具查看，发现数据已经成功生成，如图：

笔记参考：https://blog.csdn.net/u014553029/article/details/89433709

###### 找出臭味相投的朋友，他们在所出现的所有类别（关键）里面都是朋友（并且不能有这种情况，其中一个在某个类别里出现而另外一个不出现）  
思路：  
首先得到两个表t1和t2（t1,t2均为acquaintance//可以把t1想成只有friend1和friend2的表，t2是只有class的表）  
排除掉并未出现在全部类别中的情况（就得到了在全部类别里都是朋友的情况）【  
排除掉出现在全部类别中的情况【  
从acquantance表中找出满足下列三个条件的select_result:  
抽出acquaintance表中的friend1,friend2这一朋友对，  
将这一朋友对所属的关系与t2中的相比
acquaintance表中的关系与t2(与acquaintance表相同）表中的关系完全相同  
（如果这两人出现在所有类别，那么完全相同；如果并非出现在所有类别中，一定无法完全相同）；  
】  
】  

SQL语句如下：  
select friend1,friend2,class    
from(select * from acquaintance)t1    
where not exists  
(  
   select *  
   from  
   (select * from acquaintance)t2  
   where not exists  
  (  
   select * from acquaintance    
   where class=t2.class    
   and(friend1=t1.friend1 and friend2=t1.friend2)  
   or  
   (friend1=t1.friend2 and friend2=t1.friend1)  
    )  
);  
//第二种    
select f1,f2,class from @tab t1  
where not exists (select * from @tab t2  
where not exists(select * from @tab where class=t2.class   
and ((f1=t1.f1 and f2=t1.f2) or (f1=t1.f2 and f2=t1.f1))));  

