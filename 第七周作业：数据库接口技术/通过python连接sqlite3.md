通过python连接sqlite3的步骤如下：
首先要安装好sqlite3,打开cmd输入sqlite3测试是否可以连接
之后打开python输入以下代码：
import sqlite3

# 创建并连接数据库py_demo.db
conn = sqlite3.connect("py_demo.db3")

# 创建游标
cur = conn.cursor()

# 通过cur.execute执行sql语句，操作数据库
# 1.创建表demo
cur.execute("""
    create table demo (id INT not null, name varchar(20));
""")

# 2.插入数据到表demo
cur.execute("insert into demo (id, name) values (1, 'richard');")
cur.execute("insert into demo (id, name) values (2, 'bluce');")
cur.execute("insert into demo (id, name) values (3, 'grace');")
cur.execute("insert into demo (id, name) values (4, 'jhon');")
cur.execute("insert into demo (id, name) values (5, 'nio');")

# 3.查询表
cur.execute("""
select * from demo where id=3;
""")
print(cur.fetchall())   # 打印所有的查询的结果

# 提交修改
conn.commit()

# 关闭数据库连接
conn.close()

返回结果运行截图如下：
![image]https://github.com/wuruiwen2000/-/blob/master/%E7%AC%AC%E4%B8%83%E5%91%A8%E4%BD%9C%E4%B8%9A%EF%BC%9A%E6%95%B0%E6%8D%AE%E5%BA%93%E6%8E%A5%E5%8F%A3%E6%8A%80%E6%9C%AF/python%E8%BF%9E%E6%8E%A5sqlite3%E8%BF%94%E5%9B%9E%E7%BB%93%E6%9E%9C.PNG
