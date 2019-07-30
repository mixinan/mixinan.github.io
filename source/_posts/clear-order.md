---
title: 数据库自动删除超时订单
date: 2019-07-24 20:05
---

15分钟后，删除订单

<!--more-->

## 建库 db1、建表 table1
```
create  database  db1;
use db1;

create table table1 (
    id int primary key auto_increment,
    name varchar(20),
    age int,
    addtime datetime default now()
);
```

## 创建存储过程
```sql
# 把SQL语句的结束符，从默认的 “;” 改为 “#”
delimiter #

# 创建存储过程 clear_order()
# 删除900秒之前添加的记录
create procedure clear_order()
begin
    delete from table1 
      where now()-addtime>900;
end#

# 把SQL语句的结束符，改回默认的 “;”
delimiter ;

# 查询数据库db1里的存储过程
select * from mysql.proc 
    where db="db1";

# 列数较多，显示很乱
# 可以把“;”改为"\G"
# 以列表形式显示结果
select * from mysql.proc
    where db="db1"\G
```
## 创建事件调度器
```sql
# 查看“事件调度器”的状态
show variables like "%event_scheduler%";

# 开启“事件调度器”
set global event_scheduler=on;

# 创建定时事件 clear_order_event
# 从2019-7-24 20:17:00起
# 每秒执行一次 clear_order()

create event clear_order_event 
on schedule
every 1 second
starts '2019-7-24 20:17:00'
do call clear_order();

# 查看数据库db1里的事件
select * from mysql.event
    where db="db1"\G
```

## 使用存储过程
```
call clear_order();
```

## 删除事件、删除存储过程
```
drop event clear_order_event;
drop procedure clear_order;
```