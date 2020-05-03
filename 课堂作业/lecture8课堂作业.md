### 1.测试使用用户权限控制的语句  
#### 1)授权命令语句（授予查询和插入的权利）：
##### grant select,insert on acquaintance to user_second
##### [with grant option]//可以再授予其他人
#### 2)回收权限（撤回插入数据的权利）：
##### revoke insert on acquaintance from user_second
#### 3）用户的存取控制
##### declare @user char(30)
##### set @user=user
##### select 'The current user is:'+@user
##### select * from acquaintance
##### where friend1=user
#### 4）角色的存取控制
##### //创建角色
##### create role 'app_developer';
##### //赋予角色权限
##### grant all on 'app_developer';
##### //赋予账户角色
##### GRANT 'app_developer' TO 'user_second'@'localhost';
#### 5）限制账户资源
##### with max_queries_per_hour 20;
2.MySQL批处理的功能：
备份mysql数据库时使用到了批处理文件进行定时导出
有多条SQL语句需要送到数据库执行的时候，可以进行批处理，提高数据库的执行效率
