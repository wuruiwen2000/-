# 1.通过MySQL函数连接MySQL数据库函数
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
###https://github.com/wuruiwen2000/-/blob/master/%E7%AC%AC%E4%B8%83%E5%91%A8%E4%BD%9C%E4%B8%9A%EF%BC%9A%E6%95%B0%E6%8D%AE%E5%BA%93%E6%8E%A5%E5%8F%A3%E6%8A%80%E6%9C%AF/%E6%95%B0%E6%8D%AE%E5%BA%93%E7%AC%AC%E4%B8%80%E9%A2%98%E7%94%A8mysql%E5%87%BD%E6%95%B0%E6%9D%A5%E9%93%BE%E6%8E%A5.PNG
