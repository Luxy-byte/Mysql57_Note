# DELETE删除数据

> delete命令

**语法：DELETE FROM 表名 [WHERE 条件]**

```sql
-- 删除全部数据
DELETE FROM `student`; -- 不会影响自增

-- 删除指定数据
DELETE FROM `student` WHERE id=1;
```



> TRUNCATE 命令

作用：完全清空一个数据库表，表的结构和索引约束不会发生改变

```sql
TRUNCATE `usermag`; -- 自增清零
```



> 区别

- 相同点：都能删除数据，都不会删除表结构

- 不同：

  - TRUNCATE 重新设置自增列，计数器会归零
  - TRUNCATE 不会影响事务

  

> 了解	

DELETE删除的问题，重启数据库，现象

- INNODB： 自增列会从1开始（存在内存当中，断电即失）
- MyISAM： 继续从上一个自增量开始 (存在文件中，不会丢失)

