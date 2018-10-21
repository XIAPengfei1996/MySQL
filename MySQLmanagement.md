最近做了很多事情，以至于把MySQL的学习搁置了半个月。
由于时间紧迫，不只是视频，连书本都算不上高效的学习材料，好在常用的软件或者语言，网上都有很多优秀的网页教程，学习效率非常高。
我这里主要参考的是[RUNOOB菜鸟教程](http://www.runoob.com/mysql/mysql-tutorial.html)。
简单再说一下为什么要学SQL。SQL之于Excel VBA，好比计算器之于计算机，火车之于卡车；虽然有失灵活，但是规范，稳定，更重要的是高效。
程序员的时间比CPU时间宝贵，效率就是生产力。

[下载](https://dev.mysql.com/downloads/mysql/)和安装都是傻瓜式的操作，按照指令操作就行。如果实在此不赘述。

```MySQL
PATH="$PATH":/usr/local/mysql/bin
mysql -u root -p
Enter password: # 输入密码
```

## MySQL管理

用 insert 命令添加用户时，可能会报错:
```MySQL
ERROR 1364 (HY000): Field 'ssl_cipher' doesn't have a default value
```
my-default.ini中有一条语句：
指定了严格模式，为了安全，严格模式禁止通过 insert 这种形式直接修改 mysql 库中的 user 表进行添加新用户
因此也可以将 STRICT_TRANS_TABLES 删掉之后即可使用 insert 添加新用户
```MySQL
sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES
```

注意：在 MySQL5.7 中 user 表的 password 已换成了authentication_string。
注意：password() 加密函数已经在 8.0.11 中移除了，可以使用 MD5() 函数代替。

添加新用户建议使用 grant 命令
```MySQL
# 创建新用户guest
create user 'guest'@'localhost' IDENTIFIED BY '******'; # 此处星号应填密码
# 授予指定权限
grant SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,ALTER on *.* to 'guest'@'localhost';
# 授予所有权限
grant all Pprivileges ON *.* to 'guest'@'localhost';
# 查看用户guest的权限：
show grants for 'guest'@'localhost';
# 查看当前用户（自己）权限：
show grants;
# 使用grant option选项，将授权权限授予其他用户
grant select on *.* to guest@localhost with grant option;
```
这个选项一般用不到。因为实际中，数据库权限最好仅由DBA来统一管理。

使用 revoke 命令撤销已经赋予给 MySQL 用户权限的权限。
```MySQL
revoke all on *.* from guest@localhost;
```
revoke 跟 grant 的语法差不多，只需要把关键字 to 换成 from 即可