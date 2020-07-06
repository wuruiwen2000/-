#### 完成分类修改页面的ORM操作改造（文章总共有author,title,class,publishtime，ID）
代码如下：
(<?php  
// 选择数据库  
include('conn.php');  

$id=$_GET["ID"];  
// 获取修改的种类  

$class=$_GET["class"];  
$author= $_POST['author'];  
$title = $_POST['title'];  
$class = $_POST['class'];  
$uploadTime = $_POST['uploadTime'];  


// 插入新的分类  
mysqli_query($conn,"UPDATE termbase SET   
            class='$class'   
			WHERE id = '$id'")   
			
or die('添加数据出错：'.mysqli_error($conn));   
？>)  
### 完成文章添加、修改的ORM操作改造 （文章总共有author,title,class,publishtime，ID）  
文章添加--  
代码如下：  
（<?php  
// 连接mysql  
$link = @mysql_connect('localhost:3304','root','root') or die("提示：数据库连接失败！");  
// 选择数据库  
mysql_select_db('project1',$link);  
// 编码设置  
mysql_set_charset('utf8',$link);  
  
// 获取增加的新闻   
$class= $_POST['class'];    
$author = $_POST['author'];    
$title = $_POST['title'];  
$publishTime = $_POST['publishTime'];  
  
// 插入数据  
mysql_query("INSERT INTO termbase(class,author,title,publishTime) VALUES ('$class','$author','$title','$publishTime')",$link) or die('添加数据出错：'.mysql_error());   
if('mysql_query')  
{
die("您的文章添加完毕");  
}  
?>）  

文章修改--  
代码如下：
(<?php  
// 选择数据库  
include('conn.php');  

$id=$_GET["id"];    
// 获取修改的术语    

$class= $_POST['class'];    
$author = $_POST['author'];    
$title = $_POST['title'];    
$publishTime = $_POST['publishTime'];    


// 插入数据  

mysqli_query($conn,"UPDATE termbase SET   
           class='$class', author='$author', title='$title', publishTime='$publishTime',   
			WHERE id = '$id'")   
			
or die('添加文章出错：'.mysqli_error($conn));   
？>）

