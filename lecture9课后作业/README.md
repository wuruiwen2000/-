### 题目一
### 完成apache+MySQL+PHP基础开发环境的工作
#### 此开发环境可以手动配置，也可以直接选择直接安装XAMPP。(XAMPP（Apache+MySQL+PHP+PERL）是一个功能强大的建站集成软件包。)
#### 安装后点击按钮，可以在网页中看到数据库的信息。
![image](https://github.com/wuruiwen2000/-/blob/master/lecture9%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/9%E8%AF%BE%E5%90%8E-1.PNG)

### 选作：完成Nginx-uwsgi-MySQL-Python基础开发环境的工作

### 题目二
### 完成php调试工具的安装、配置和使用：
### 需要：(pycharm),phpstorm(xdebug),chrom xdebug helper
### Xdebug helper chrome插件的安装：
#### 从插件下载地址：(http://www.cnplugins.com/devtool/xdebug-helper/)下载Xdebug helper
#### 离线安装的方法：
#### 在标签页输入【chrome://extensions/】进入chrome扩展程序，解压下载的插件，并拖入扩展程序页面，它会提示你是否安装该插件，点击添加即可。
#### 直接拖放安装时会出现“程序包无效CRX-HEADER-INVALID”的报错信息，解决方法：
#### 将下载的CRX格式的文件修改成Zip格式的文件（方法是显示文件的扩展名之后直接在后面修改）
#### 用解压缩工具将ZIP格式的文件解压
#### 解压后得到的文件如下图：
![image](https://github.com/wuruiwen2000/-/blob/master/lecture9%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/lecture9%E8%AF%BE%E5%90%8E%E4%BD%9C%E4%B8%9A/zip.PNG)
#### 打开chrome扩展程序管理页面（更多工具->拓展程序),点击“加载已解压的扩展程序”。
#### 下载phpstorm后，进行如下图的配置：
#### 写好php文件后，点击监听模式，在网页中点击图标下的debug，即可在PHPstorm-debugger处以及网页（localhost打开）里看到显示
![image]
![image]
### 题目三
### 安装、调试并使用PHP/python的一种ORM框架的使用，并编写自己的测试案例与代码
什么是ORM框架：对象关系映射（Object Relational Mapping，简称ORM）是一种为了解决面向对象与关系数据库存在的互不匹配的现象的技术。 简单的说，ORM是通过使用描述对象和数据库之间映射的元数据，将程序中的对象自动持久化到关系数据库中。本质上就是将数据从一种形式转换到另外一种形式。ORM提供了所有SQL语句的生成，代码人员远离了数据库概念。从一个概念需求(例如一个HQL)映射为一个SQL语句，并不需要什么代价，连1%的性能损失都没有。真正的性能损失在映射过程中，更具体地讲，是在对象实例化的过程中。
### PHP的ORM框架
- READBEAN框架的下载： 
在(https://redbeanphp.com/index.php?p=/download)网页中下载Download RedBeanPHP 5 mysql,解压后得到一个txt和一个rb-mysql.php
- 调试及使用：
- - 需要：php
- - 在命令行中输入echo dram.php，notepad.exe dram.php创建php文件
- - 在该php文件中键入测试代码，代码如下：
require'rb-sql.php';
R::setup();
$bean = R::dispense('email');
$bean->subject = 'Read this email';
$bean->date = date('Y-m-d H:i:s', time());
$id = R::store($bean);
$email = R::load('email', $id);
var_dump($email);
### Python的ORM框架
- sqlchemy的安装： 
- - 通过pip语句直接安装：pip install sqlchemy
- - 安装包安装：通过网址https://docs.sqlalchemy.org/en/13/安装
- 调试及使用
- 创建连接对象：
from sqlalchemy import create_engine # 连接本地test数据库 engine = create_engine("mysql+pymysql://root:root@localhost/test?charset=utf8") 
- 简单使用：
result = engine.execute("select * from news")  
print(result.fetchall()) (1, '本机新闻标题'), (2, '今天的新闻'), (3, '新闻标题1'), (4, '新闻标题2'), (5, '元组新闻1'), (6, '元组新闻2')  
- 创建映射：
- - 创建一个infos.py，映射数据表：
from sqlalchemy.ext.declarative import declarative_base 
Base = declarative_base() 
from sqlalchemy import Column, Integer, String 
class News(Base):   
#表名称   
__tablename__ = 'news'  
#news表里id字段   
id = Column(Integer, primary_key=True, autoincrement=True)   
#news表里title字段   
title = Column(String(length=255), nullable=False) 
from sqlalchemy import create_engine from mappers.Infos import News 
from sqlalchemy.orm import sessionmaker 
#连接本地test数据库 engine = create_engine("mysql+pymysql://root:root@localhost/test?charset=utf8") 
#创建会话 session = sessionmaker(engine) mySession = session() 
#查询结果集 
result = mySession.query(News).all() print(result[0]) 
- 查询（查询第一条记录）：
result = mySession.query(News).first() print(result.title) #打印对象属性 

参考：https://www.jianshu.com/p/243168fa358d
https://www.oschina.net/p/redbeanphp/related?lang=0&p=21&sort=view




