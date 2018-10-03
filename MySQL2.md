# 第0章 MySQL学习指南


## 什么是数据库

数据库分三类：
1. 层次式数据库
2. 网络式数据库
3. 关系型数据库

共同属性/特点：
- 采用特定的数据类型；
- 增加数据共享，减少数据冗余；
- 具有较高的数据独立性；
- 具有统一的数据控制功能。

数据库系统包括3个主要组成部分：
1. **数据库（DataBase, DB)**：用于储存数据的存储空间；
2. **数据库管理系统（DataBase Management System, DBMS)**：用于管理数据库的软件；
3. 数据库应用系统（DataBase Application)：为了提高数据库系统处理能力的管理软件补充，直观而友好；

**结构化查询语言（Structured Query Language, SQL）**:用来实现对数据库进行查询和修改操作的标准语言。

SQL语言包含4个部分：
1. 数据定义语言（DDL）：drop，create，alter等语句；
2. 数据操作语言（DML）：insert，update，delete语句；
3. 数据查询语言（DQL）：select语句；
4. 数据控制语言（DCL）：grant，revoke，commit，rollback等语句。


## MySQL简介

MySQL是一个开放源码的小型关系型数据库管理系统。优点是开源，免费，安全，体积小，速度快，跨平台，多用户，多线程；缺点是规模小，功能有限。

流行的网站构架方式LAMP：Linux作为操作系统，Apache作为Web服务器，MySQL作为数据库，PHP作为服务器端脚本解释器。

MySQL的海豚标志名叫“sakila”，斯威士兰方言，坦桑尼亚小镇名字

![logo](https://www.seeklogo.net/wp-content/uploads/2017/05/mysql-logo.png)


## MySQL的技术体系

1. C/S架构：客户机/服务器（client/server）架构；
2. MySQL命令行实用程序
3. MySQL Workbench：ER/数据库建模工具，主要功能有数据库设计与建模，SQL开发，数据库管理。


## MySQL的应用领域和前景（略）


## MySQL学习经验谈

多写多实践


## MySQL学习路线图

1. 基础知识
2. 核心技术
3. 高级应用
4. 项目实战