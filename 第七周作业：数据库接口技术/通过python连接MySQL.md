# 通过python连接MySQL
## 第一种方法（）步骤如下：
### a.到Python官网下载python(executer-version）
### b.记得勾选pip安装包
### c.为Python和MYSQL连接做准备：打开cmd，直接在C:\users\Administrator>下写pip install pymysql
### 注：其中安装包出现Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ConnectTimeoutError情况
### 解决办法：
### 先输入 pip install selectivesearch -i http://pypi.douban.com/simple --trusted-host pypi.douban.com，
### 后再输入pip install mysql
### d.打开python shell开始编写python代码
### import pymysql
### conn = pymysql.connect(host='127.0.0.1', user = "root", passwd="012025", db="acquaintance", port=3306, charset="utf8")
### //passwd为数据库密码，db为数据库中想要查找的表的名字
### cursor=conn.cursor()
### //# 使用cursor()方法获取操作游标
### //开始select:
### //选择表中的全部数据：
### sqlquery="select * from t1";
### try:
### 	cursor.execute(sqlquery)
### 	results=cursor.fetchall()
### 	for row in results:
### 		friend1=row[0]
### 		relationship=row[1]
### 		print('friend1:%s,relationship:%s'%(friend1,relationship))
### except pymysql.Error as e:
### 	print("数据查询失败:"+str(e))
### //进行条件选择：
### sqlquery="select * from t1 where person='1'";
### try:
### 	cursor.execute(sqlquery)
### 	results=cursor.fetchall()
### 	for row in results:
### 		friend1=row[0]
### 		relationship=row[1]
### 		print('friend1:%s,relationship:%s'%(friend1,relationship) )
### except pymysql.Error as e:
### 	print("数据查询失败:"+str(e))
### //其中出现SyntaxError: multiple statements found while compiling a single statement错误，解决办法：逐条执行
