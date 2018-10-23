## 使用 create 命令创建数据库

创建一个数据库名为nutrition的数据库
```MySQL
create database nutrition;
```

也可以使用 mysqladmin 创建数据库
```MySQL
mysqladmin -u root -p create nutrition
Enter password: # 输入密码
```

使用root登录后，还可以使用
create database if not exists nutrition default charset utf8 collate utf8_general_ci;
创建数据库，该命令的作用：
1. 如果数据库不存在则创建，存在则不创建。
2. 创建RUNOOB数据库，并设定编码集为utf8


## 使用 drop 命令删除数据库

注意：删除数据库操作时务必万分谨慎！

删除一个数据库名为nutrition的数据库
```MySQL
drop database nutrition; 
# 执行此命令后，会出现一个确认提示框
Dropping the database is potentially a very bad thing to do.
Any data stored in the database will be destroyed.
# 输入y确认删除
Do you really want to drop the 'nutrition' database [y/N] y
Database "nutrition" dropped
```


## 使用 use 命令选择数据库

选择一个数据库名为nutrition的数据库来进行进一步操作
```MySQL
use nutrition;
Database changed
```