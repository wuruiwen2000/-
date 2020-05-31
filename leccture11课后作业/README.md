### 题目：测试Apache和nginx的各种配置；编码并测试运行课件中留言板的代码功能，并熟练理解代码原理
### 留言本案例（Web开发）实践：
表单提交，数据接收，写入数据库，读出数据库，分页
创建数据库和表(Message表存放用户提交的留言以及管理员的回复。
Admin用来存放管理员的用户名和密码)：
//创建数据库gbook;
CREATE DATABASE `gbook` ;

//创建表admin;
CREATE TABLE `admin` (
`username` VARCHAR( 20 ) NOT NULL ,
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

登录页面设计：send.php
#### 注意：想要登录进页面，需要先在数据库的表admin里面，添加好用户名和密码（“coconut”——“test”），之后就可以在网页中登录了
->manage.php

