使用的为之前world数据库中的city表
city表中包括ID,Name,CountryCode,District,Population几项
存储过程的练习（SQL语句如下）

触发器:
行级触发器
(2)

准备工作：
-- 创建表exercise1
-- 创建表exercise2
practice1:
新增一条记录，触发另一张表的新增
创建触发器：t_afterinsert_on_exercise1
作用：增加tab1表记录后自动将记录增加到tab2表中
drop trigger if exists t_afterinsert_on_exercise1;
delimiter $
create trigger t_afterinsert_on_exercise1
after insert on exercise1
for each row
begin 
insert into exercise2(tab2_id) values(new.tab1_id)
end$
delimiter ;
测试语句：
insert into exercise(tab1_id) values('0001');
select * from exercise1;
select * from exercise2;

practice2:删除一条记录，触发另一张表的删除
drop trigger if exists t_afterdelete_on_exercise1;
delimiter $
create trigger t_afterdelete_on_exercise1
after delete on exercise1
for each row
begin
delete from exercise2
where tab2_id=old.tab1_id;

end$
delimiter ;
测试语句：
delete from exercise1 where tab1_id='0001';
select * from exercise1;
select * from exercise2;
