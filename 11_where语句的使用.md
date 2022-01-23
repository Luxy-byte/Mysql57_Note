# where条件,模糊查询

作用：检索数据中，符合条件的值

> 逻辑运算符

| 运算符  | 语法             | 描述        |
| ------- | ---------------- | ----------- |
| and &&  | a and b; a&&b    | 与,两真为真 |
| or \|\| | a or b; a \|\| b | 或,一真为真 |
| Not !   | not a; ! a       | 非,真假互换 |

```sql
-- AND 用法
SELECT result.StudentNo,result.StudentResult FROM result WHERE result.StudentResult >= 95 AND result.StudentResult < 100

-- 模糊查询
SELECT result.StudentNo,result.StudentResult FROM result WHERE result.StudentResult BETWEEN 95 AND 100

-- 非
SELECT result.StudentNo,result.StudentResult FROM result WHERE NOT result.StudentNo=1
SELECT result.StudentNo,result.StudentResult FROM result WHERE result.StudentNo!=1
```



# 模糊查询

> 比较运算符

| 运算符      | 语法               | 描述                         |
| ----------- | ------------------ | ---------------------------- |
| IS NULL     | a is null          | 如果操作符为null，结果为真   |
| IS NOT NULL | a is not null      | 如果操作符不为null,结果为真  |
| BETWEEN     | a between b and c  | 若 a在 bc之间 则为真         |
| Like        | a like b           | a 能匹配到 b，则为真         |
| IN          | a in (a1,a2,a3,a4) | 假设a在a1,a2,a3...则结果为真 |

```sql
LIKE 用法
-- 查询名字中带赵的同学
-- % （代表0到任意个字符）
-- _ （代表一个字符）
SELECT student.StudentNo,student.StudentName FROM student WHERE student.StudentName LIKE '赵%'

-- 查询姓赵同学,名字后面只有一个字的
SELECT student.StudentNo,student.StudentName FROM student WHERE student.StudentName LIKE '赵_'

-- 查询姓赵同学,名字后面只有两个字的
SELECT student.StudentNo,student.StudentName FROM student WHERE student.StudentName LIKE '赵__'

-- 查询名字中间有马字的同学
SELECT student.StudentNo,student.StudentName FROM student WHERE student.StudentName LIKE '_马%'

IN 用法
-- IN 范围是具体的一个值或者多个值，%_ 失效
-- 查询学生号在 1001，1002，1003 的学生
SELECT student.StudentNo,student.StudentName FROM student WHERE student.StudentNo IN (500,501,502)

-- 查询在北京，四川，陕西的学生 （必须是具体的值）
SELECT student.StudentNo,student.StudentName FROM student WHERE student.Address IN ('四川','北京')

IS NULL 或者 IS NOT NULL
SELECT student.StudentNo,student.StudentName FROM student WHERE student.Phone='' OR student.Phone IS NULL 
```

