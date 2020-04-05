# 通过php连接MySQL数据库
## 1.通过MySQL函数连接MySQL数据库函数
## 并提取了数据库中某列的内容
## PHP文件代码如下：
#### <?php
#### $server="localhost";
#### $username="root";
#### $password="012025";
#### $link=mysqli_connect($server,$username,$password);
#### if($link)
#### {
#### echo"数据库已经成功连接了！";
#### echo"<br>";
#### }
#### //连接数据库


#### echo"下面开始呈现提取出的数据";
#### mysqli_select_db($link,"world");

#### $result=mysqli_query($link,$query);
#### //获得结果


#### if(!$result)
#### {
#### die("Coule not get data:".mysqli_error());
#### }
#### while($row=mysqli_fetch_array($result,MYSQLI_BOTH))
#### {
#### echo "城市名字:{$row['Name']}  <br> ".
####          "--------------------------------<br>";
#### } 
#### 	echo "成功加载所有数据\n";
#### mysqli_close($link);
#### ?>

### 需要：XAMPP
### MySQL和php网页是无法直接连接的，需要XAMPP作为中间项，将Apache和MySQL打开，从而使得我们可以从网页上直接看到数据库连接后的结果
### 写好的网页可以放在hotdocs下面，通过localhost来访问，直接访问localhost/demotest.php即可
### 简单查询及返回结果如下截图所示：![image](https://github.com/wuruiwen2000/-/blob/master/%E7%AC%AC%E4%B8%83%E5%91%A8%E4%BD%9C%E4%B8%9A%EF%BC%9A%E6%95%B0%E6%8D%AE%E5%BA%93%E6%8E%A5%E5%8F%A3%E6%8A%80%E6%9C%AF/%E6%95%B0%E6%8D%AE%E5%BA%93%E7%AC%AC%E4%B8%80%E9%A2%98%E7%94%A8mysql%E5%87%BD%E6%95%B0%E6%9D%A5%E9%93%BE%E6%8E%A5.PNG)

## 2.通过pdo函数连接MySQL数据库
## 并将数据库中的某些数据经过查询后导入至新的数组
## PHP代码文件如下：
### <?php
### $pdo = new PDO("mysql:host=localhost;dbname=world" ,"root","012025");
### if($pdo)
### {
### echo"数据库已经成功连接啦！";
### }
### //以上为连接数据库
### echo"<br>";
### echo"下面所做的是将city表中的Name和CountryCode字段存到data数组中:";
### echo"<br>";
### 
### $result=$pdo->query("select Name,CountryCode from city");
### $data=[];
### 
### while($row=$result->fetch(\PDO::FETCH_ASSOC))
### {
### $data[]=$row;
### }
### echo'<pre>';
### print_r($data);
### echo'</pre>';
### ?>
### ///将city表中的Name和CountryCode字段存到data数组中
### 简单查询及返回结果如下图所示：
！[image](https://github.com/wuruiwen2000/-/blob/master/%E7%AC%AC%E4%B8%83%E5%91%A8%E4%BD%9C%E4%B8%9A%EF%BC%9A%E6%95%B0%E6%8D%AE%E5%BA%93%E6%8E%A5%E5%8F%A3%E6%8A%80%E6%9C%AF/%E6%95%B0%E6%8D%AE%E5%BA%93%E7%AC%AC%E4%BA%8C%E9%A2%98%E7%94%A8PhP%E9%80%9A%E8%BF%87pdo%E8%BF%9E%E6%8E%A5MySQL%E6%95%B0%E6%8D%AE%E5%BA%93.PNG)
