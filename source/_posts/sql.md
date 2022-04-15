---
title: sql
categories:
  - 开发
tags:
  - sql
  - mysql
date: 2022-04-16 01:28:03
---

# ppt1-4 erd关系图

## 1.实体类（对象）是什么

实体简单而言就是一张表的一行，通常情况，一行拥有很多列（属性），而多个实体也就组成了实体类表格



## 2.erd是什么

简而言之就是描述实体类（表）之间关系的图

<!--more-->

## 3.erd关系罗列

<img src="\images\sql\1.png" alt="erd关系图" style="zoom:75%;" />

**具体示例可以看** https://www.bilibili.com/video/BV1HC4y1W7w8



## 4.强/弱实体

弱实体只是一个实体，它的存在依赖于另一个实体。如：在缺少员工（employee）表的情况下，您无法在逻辑上拥有依赖（儿子，女儿，..等）。它的轮廓与普通实体相同，但需要双划线标注。

**具体参考 ppt3 20**



## 5.在多对多关系中，可以合理建立“桥表”

桥表就是第三张表，一般是弱实体表，可以去维护其他两张表的关系，以及更多细节。比如顾客和产品，就有多对多关系，可以建立订单表，订单表就可以记录订单时间之类的其他数据



## 6.主键/外键 

主键特点：1.唯一

				    2.不能改变
	
	                3.不能为空

外键：一般是两表关联的字段，通常为其他表的主键。比如在订单表中含有顾客id（顾客表主键），或者产品id（产品表主键），那么这两个字段在订单表中就是外键，一张表可以有多个外键。



## 7.三大范式 （NF）

1NF：**要求数据库表的每一列都是不可分割的原子数据项。**

2NF：**在1NF的基础上消除部分依赖**

          *需要确保数据库表中的每一列都和主键相关，而不能只与主键的某一部分相关（主要针对联合主键而言）*

3NF：**在2NF基础上消除传递依赖**

          *需要确保数据表中的每一列数据都和主键直接相关，而不能间接相关*

具体参考 文字：https://www.cnblogs.com/wsg25/p/9615100.html

                 视频：https://www.bilibili.com/video/BV1uJ411k7wy?p=518





# ppt5-6 SQL



## 1.什么是sql

**SQL 是用于访问和处理数据库的标准的计算机语言**



## 2.数据库的关系

一台电脑可以拥有多个数据库（database），一个数据库可以拥有多个数据表（table）

<img src="\images\sql\2.png" alt="2" style="zoom:75%;" />

## 3.SQL语言的分类

<img src="\images\sql\3.png" style="zoom:67%;" />

**1. 数据查询语言DQL**(重点) 数据操做-查询
1.SELECT 

**2 .数据操纵语言DML**(重点) 数据操做-增删改

1.插入：INSERT
2.更新：UPDATE
3.删除：DELETE

**3. 数据定义语言DDL** 数据库/表结构操做
1.创建：CREATE
2.更新：ALTER
3.删除：DROP

**4. 数据控制语言DCL(一般了解即可，用到再百度)**
简而言之就是授权（比方用户A可以看到表A，而用户B不能看到表A，超级用户可以对表进行删除之类的权限分配与操做）



## 4.SELECT

```sql
SELECT 列名称 FROM 表名称
```



## 5.INSERT

```SQL
INSERT INTO 表名称 VALUES (值1, 值2,....)
```

我们也可以指定所要插入数据的列

```SQL
INSERT INTO 表名称 (列1, 列2,...) VALUES (值1, 值2,....)
```



## 6.UPDATE

```sql
UPDATE 表名称 SET 列名称 = 新值 WHERE 列名称 = 某值
```



## 7.DELETE

```SQL
DELETE FROM 表名称 WHERE 列名称 = 值
```



## 8.查询条件where

—<, >, <=, >=, !, !=,…

—LIKE

—NOT, AND, OR

—BETWEEN

—IN

—IS NULL

—IS NOT NULL



## 9.函数

MIN, MAX, COUNT, SUM, AVG。。。



## 10.排序

ORDER BY

desc倒序



## 11.分组

group by

分组后过滤，having



## 12.高级查询

- 多表联查

  1.内连接inner join

  2.外连接

  		1）左外连接 LEFT
		
  	    2）右外连接 RIGHT

- 子查询(课件里没讲)



# 参考地址

视频.https://www.bilibili.com/video/BV1Kr4y1i7ru

文字.https://www.w3school.com.cn/sql/sql_join_left.asp
