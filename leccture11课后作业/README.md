### 题目：测试Apache和nginx的各种配置；编码并测试运行课件中留言板的代码功能，并熟练理解代码原理
### 留言本案例（Web开发）实践：
表单提交，数据接收，写入数据库，读出数据库，分页  
创建数据库和表(Message表存放用户提交的留言以及管理员的回复;Admin用来存放管理员的用户名和密码)：   
//创建数据库gbook;    
CREATE DATABASE `gbook` ;  
  
//创建表admin;  
CREATE TABLE `admin` ( 
'username' NULL ,
`userpass` VARCHAR( 20 ) NOT NULL 
)

//创建表message：
CREATE TABLE `message` (
`id` INT( 4 ) NOT NULL AUTO_INCREMENT PRIMARY KEY ,
`author` VARCHAR( 20 ) NOT NULL ,
`addtime` DATETIME NOT NULL ,
`content` VARCHAR( 1000 ) NOT NULL ,
`reply` VARCHAR( 1000 ) NOT NULL 
)

#### 整体实践：
##### ->先进入网站login.php
![iamage](https://github.com/wuruiwen2000/-/blob/master/leccture11%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/login%E7%95%8C%E9%9D%A2.PNG)
#### 注意：想要登录进页面，需要先在数据库的表admin里面，添加好用户名和密码（“coconut”——“test”），之后就可以在网页中登录了
![iamge](https://github.com/wuruiwen2000/-/blob/master/leccture11%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/%E7%99%BB%E5%BD%95%E6%88%90%E5%8A%9F.PNG)

##### ->进行用户登录，进入manage.php
![image](https://github.com/wuruiwen2000/-/blob/master/leccture11%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/%E7%AE%A1%E7%90%86%E5%91%98%E7%99%BB%E9%99%86%E7%AE%A1%E7%90%86%E7%95%99%E8%A8%80manage%E7%95%8C%E9%9D%A2.PNG)
##### -->可以回复留言，进入reply.php
普通人员回复：
![image](https://github.com/wuruiwen2000/-/blob/master/leccture11%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/reply%E7%95%8C%E9%9D%A2.PNG)
管理人员回复：
![image](https://github.com/wuruiwen2000/-/blob/master/leccture11%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/%E5%9B%9E%E5%A4%8D%E7%BB%93%E6%9E%9C.PNG)
##### -->可以删除留言，以下为删除成功页面
![image](https://github.com/wuruiwen2000/-/blob/master/leccture11%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/%E5%88%A0%E9%99%A4%E7%95%8C%E9%9D%A2.PNG)
##### ->点击“注销登录”，回到logout.php
##### ->直接留言，进入send.php
##### ->查看留言结果，进入index.php
![image](https://github.com/wuruiwen2000/-/blob/master/leccture11%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/%E7%95%99%E8%A8%80%E6%9D%BF%E5%85%A8%E4%BD%93%E5%86%85%E5%AE%B9.PNG)

##### ->回复留言，（注意：必须提前登录好！）进入reply.php

