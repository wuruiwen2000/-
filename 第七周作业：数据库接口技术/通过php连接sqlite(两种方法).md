1.普通方式
代码如下：
<?php
 
# 连接SQLite数据库，appAll.db
$db = new SQLite3(dirname(__FILE__).'appAll.db');
# 设置数据库编码为utf-8（防止乱码）
$db->exec('set names utf8');

$sql = "
    CREATE TABLE `user` (
      `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
      `name` varchar(50) NOT NULL COMMENT '用户名',
      `create_time` int(10) unsigned NOT NULL,
      `update_time` int(10) unsigned NOT NULL,
      PRIMARY KEY (`id`)
    ) ENGINE=MyISAM AUTO_INCREMENT=1 DEFAULT CHARSET=utf8 COMMENT='用户表';
";
$res = $db->query($sql); 
if($res){
    echo '创建表成功<br/>';
}else{
    echo '创建表失败<br/>';
}
 
$res = $db->querySingle("select name from user");
if($res){
    echo '【查询单个字段：】<pre>';
    print_r($res);
    echo '</pre>';
}else{
    echo '没有数据<br/>';
}
 
 2.利用PDO方式，适用于sqlite更早的版本
 <?php
header("content-type:text/html;charset=utf-8");
# 【PDO连接sqlite数据库】
$pdo = new \PDO('sqlite:'.dirname(__FILE__).'appAll.db'); 
# 设置数据库编码为utf-8
$pdo->exec('set names utf8'); 

$sql = "CREATE TABLE `user` (
      `id` int(10),
      `name` varchar(50),
      `create_time` int(10),
      `update_time` int(10),
      PRIMARY KEY (`id`)
    )
";
$res = $pdo->exec($sql); 
if($res){
    echo '创建表成功<br/>';
}else{
    echo '创建表失败<br/>';
}
 $res = $pdo->query("select id,name from user"); 
$data = [];
 
# 1：FETCH_ASSOC   关联数组形式返回 
# 2：FETCH_NUM     数字索引数组形式返回
# 设置返回数据类型方法1：
$res->setFetchMode(\PDO::FETCH_NUM); 
while($row = $res->fetch()){
    $data[] = $row;
}
echo '<pre>';
print_r($data);
echo '</pre>';
