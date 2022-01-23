# INSERT插入数据

```sql
# 插入单一数据 格式:
INSERT INTO 表名 ([字段一],[字段二],[字段三]....)values('值1','值2','值3'...);

# 列：
INSERT INTO `grade`(`gradename`) VALUES('大二');

# 插入多条数据 格式：
INSERT INTO 表名 ([字段一],[字段二],[字段三]....)values('值1','值2','值3'...),('值1','值2','值3'...),('值1','值2','值3'...);

# 列：
INSERT INTO `grade`(`gradename`) VALUES('大三'),('大四');

```

- 字段和值 必须要 一 一 对应。
- 字段和字段之间使用 英文逗号 隔开。
- 字段是可以省略的，但是值必须对应上。
- 可以同时插入多条数据，value后面的值，需要使用 ， 隔开：values（）,（）



# UPDATE修改数据

```sql
# 修改单一数据 格式：
UPDATE 表名 SET 字段名=值 WHERE [条件]

# 列：
UPDATE `student` SET `sex`='男' WHERE id = 1; -- 指定条件 改动
UPDATE `student` SET `sex`='男'			     -- 改动全部

# 修改多条数据 格式：
UPDATE 表名 SET 字段名1=值1,字段名2=值2, [....] WHERE [条件]

# 列：
UPDATE `student` SET `name`='luxh', `pwd`='13579' WHERE id BETWEEN 1 AND 3;

# 根据多个条件修改数据 无上限
UPDATE `student` SET `pwd`='13579' WHERE `name`='luxh' AND `sex`='女';
```

**条件：where子句 运算符 id等于某个值，大于某个值，在某个区间内修改**

| 操作符         | 含义     |
| -------------- | -------- |
| =              | 等于     |
| <> 或!=        | 不等于   |
| >              | 大于     |
| <              | 小于     |
| >=             | 大于等于 |
| <=             | 小于等于 |
| BETWEEN..AND.. | 包含关系 |
| AND            | && 且    |
| OR             | \|\| 或  |

> **语法：UPDATE 表名 SET colnum_name = value,[colnum_name = value,......] WHERE [条件]**

注意：

- colnum_name 是数据库的列，尽量带上``,
- 条件，筛选的条件，如果没有指定，则会修改所有的列
- value,是一个具体的值，也可以是一个标量
- 多个设置的属性之间，使用英文逗号隔开

