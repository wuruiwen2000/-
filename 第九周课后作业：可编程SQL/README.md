# 练习可编程SQL章节中的内容
### ·存储过程的编写，IN、OUT等参数的使用
###### 笔记整理：
###### 定义：将程序在服务器中编译后存储起来，应用程序向服务器发出调用请求
###### 优点：重复使用，执行效率高
###### MySQL存储过程的创建
###### ·格式
###### ·声明分隔符
###### ·参数
###### （直接打开就是数据库的phpmyadmin）
##### 使用t_user表练习：
##### // 创建数据表的语句
###### CREATE TABLE
######  t_user 
###### ( 
######  USER_ID INT NOT NULL AUTO_INCREMENT, 
######   USER_NAME CHAR(30) NOT NULL, 
######   USER_PASSWORD CHAR(10) NOT NULL, 
######   USER_EMAIL CHAR(30) NOT NULL, 
######   PRIMARY KEY (USER_ID), 
######   INDEX IDX_NAME (USER_NAME) 
######  ) 
######  ENGINE=InnoDB DEFAULT CHARSET=utf8; 
############ 使用的是数据库原理的phpmyadmin，直接打开即可，xampp可以不连接
##### //整个导入sql文件得到t_user表

#### 带in的存储过程
##### 特点：IN参数的值必须在调用存储过程时指定，在存储过程中修改该参数的值不能被返回，为默认值
#### SQL语句如下：
###### delimiter //
create procedure sp_search(in p_name char(20))
begin
if p_name is null or p_name='' then
select * from t_user;
else
select * from t_user
where user_name like p_name;
end if;
end //
delimiter ;
call sp_search('林炳文');


#调用
condition 1:
set @p_name='';
call sp_search(@p_name);
select @p_name;
condition 2:
set @p_name='林炳文';
call sp_search(@p_name);
select @p_name;

带out的储存过程：
选择带有林字的成员
delimiter //
create procedure sp_search2(in p_name char(20),out p_int int)
begin
if p_name is null or p_name='' then
select * from t_user;
else
select * from t_user where user_name like p_name;
end if;
select found_rows() into p_int;
end //
delimiter ;

#调用
call sp_search2('林%',@p_num);
select @p_num;
@p_name指的是包含这个结果的个数
