## 使用 create 语句创建数据表

create 语句创建MySQL数据表的SQL通用语法
```MySQL
create table table_name (column_name column_type);
```

比如我们在nutrition数据库中创建数据表nutrition_cfc
```MySQL
# 首先要选择数据库
use nutrition
# 创建数据表nutrition_cfc
create table if not exists `nutrition_cfc`(
   `id` int unsigned auto_increment,
   `code` varchar(100) not null,
   `name` varchar(40) not null,
   `date` date,
   primary key ( `id` )
)engine=InnoDB default charset=utf8;
```

实例解析：
1. 如果你不想字段为 NULL 可以设置字段的属性为 NOT NULL， 在操作数据库时如果输入该字段的数据为NULL ，就会报错。
2. AUTO_INCREMENT定义列为自增的属性，一般用于主键，数值会自动加1。
3. PRIMARY KEY关键字用于定义列为主键。 您可以使用多列来定义主键，列间以逗号分隔。
4. ENGINE 设置存储引擎，CHARSET 设置编码。


## 使用 drop 语句删除数据表

在nutrition数据库中删除数据表nutrition_cfc
```MySQL
# 首先要选择数据库
use nutrition
# 删除数据表nutrition_cfc
drop table nutrition_cfc
```


## 使用 insert into 语句插入数据

insert into 语句插入数据的SQL通用语法
```MySQL
insert into table_name ( field1, field2,...fieldN )
                       values
                       ( value1, value2,...valueN );
```
注意：如果数据是字符型，必须使用单引号或者双引号，如："value"。

向nutrition数据库中的nutrition_cfc数据表插入数据
```MySQL
# 首先要选择数据库
use nutrition
# 向nutrition_cfc数据表插入数据
insert into  nutrition_cfc
    (code, name, date)
    VALUES
    ("012001x", "rice", '2018-09-18');
```
注意：今天的日期和时间可以用 NOW() 函数返回。


## 使用 select 语句查询数据

select 语句查询数据的通用语法
```MySQL

SELECT column_name,column_name
FROM table_name
[WHERE Clause]
[LIMIT N][ OFFSET M]
```
1. 查询语句中你可以使用一个或者多个表，表之间使用逗号(,)分割，并使用WHERE语句来设定查询条件。
2. SELECT 命令可以读取一条或者多条记录。
3. 你可以使用星号（*）来代替其他字段，SELECT语句会返回表的所有字段数据
4. 你可以使用 WHERE 语句来包含任何条件。
5. 你可以使用 LIMIT 属性来设定返回的记录数。
6. 你可以通过OFFSET指定SELECT语句开始查询的数据偏移量。 默认情况下偏移量为0。

读取nutrition_cfc数据表输出结果
```MySQL
select  *  from  nutrition_cfc;

+-------+---------+------+------------+
| index | code    | name | date       |
+-------+---------+------+------------+
|     1 | 012001x | rice | 2018-09-18 |
+-------+---------+------+------------+
```