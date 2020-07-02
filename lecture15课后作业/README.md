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
### 完成文章添加、修改的ORM操作改造 
