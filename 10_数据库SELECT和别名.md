# DQL查询数据

- 所有的查询操作都用它 ： SELECT

- 简单的查询，复杂的查询都用它

- 数据库中最核心的语言

- 使用频率最高的语句

  

## 指定查询字段

```sql
-- 查询全部学生
SELECT * FROM 表名;
- SELECT * FROM student;

-- 查询指定字段
SELECT 表名.字段名,表名.字段名 FROM 表名;
- SELECT student.StudentName,student.GradeId FROM student;

-- 别名，给结果起一个名字 AS 可以给字段起别名 也可以给表起别名
SELECT 表名.字段名,表名.字段名 AS 别名 FROM 表名;
- SELECT student.StudentName AS '姓名',student.GradeId AS '信息' FROM student;

-- 函数 Concat(a,b)
SELECT CONCAT('姓名：', 字段名) AS 新名字 FROM 表名;
- SELECT CONCAT('姓名：',StudentName) AS '新名字' FROM student;

```

语法：SELECT 字段,......FROM 表；

>有的时候,列名字不是那么的见明知意，使用AS 起别名



> 去重 distinct

```sql
SELECT DISTINCT(去重的字段名) FROM 表;
- SELECT DISTINCT(student.StudentName) FROM student
```

> 数据库的列(表达式)

```sql
SELECT VERSION();  -- 查询系统版本 （函数）
SELECT 100*3-1 AS '计算结果' -- 用来计算 （表达式）
SELECT @@auto_increment_increment -- 查询自增的步长 （变量）

-- 学员考试成绩 + 10分，查看
SELECT result.StudentNo,result.StudentResult + 10 AS '提分后' FROM result
```

**数据库中的表达式： 文本值，列，Null，函数，计算表达式，系统表达**

**select 表达式 from 表**
