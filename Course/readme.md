## Course 讲义

从这堂课开始，我们来从 0 到 1 写一个课堂模拟器，大家有没有学过一门课？叫做《软件工程》。

《软件工程》是一门介绍软件开发全生命周期的课程，从最开始的可行性分析，顶层设计，数据流图到数据库设计，ER关系图，功能模块分析，再到程序开发和测试，最终完成软件的上线。

我凌晨的时候在思考应该怎么从 0 到 1 告诉大家，如何开发一个系统或者完成一个软件的全生命周期，我翻啊翻，终于翻到了一个蛮有趣的历史，那是四年前，2020年，我刚好大三下，软件工程的大作业。写得洋洋洒洒四万多字，有兴趣可以看看：

[软件工程大作业](https://www.zybuluo.com/PandoraKey/note/1701874)

好啦，课堂引入就是这些，在讲课堂模拟器之前，我们先考虑一个问题，如果你们是产品经理，你们想要做一个什么样子的软件，或者说产品（project），你们会用什么的方式去了解市场的需求和痛点，怎样去剖析和解决它呢？

我举几个简单的案例，这个是咱们软件技术专业大一的课程设计，算是大作业（展示课程设计的内容PDF），就单看这个信息管理系统，很多东西都涉及到信息管理，或者说任何平台的本质都是在做信息管理。

因此就引出我们要讲的一大内容——数据库

数据库的本质是在为系统构建出稳定的、可持续化的数据管理，就目前而言，我们常用到的数据库产品很多，但最常见的还是SQLite、MySQL和Oracle，而我们要用于实操的，就是MySQL。

这里介绍两种不同的数据库体验方式，第一种直接采用云数据库RDS进行部署，方便高效，且易于使用，只需要限制住白名单即可，第二种则需要进行安装和部署，然后对外映射出端口，以便于本地或其他用户使用

安装过程：

- windows：直接下载包安装即可

- ubuntu：

> sudo apt update && sudo apt install mysql-server

> sudo service mysql status

演示ubuntu裸机安装mysql，并且能够在远端机器上本地使用

创建数据库
> CREATE DATABASE 数据库名;
> create database course
>   character set utf8mb4
>   collate utf8mb4_general_ci;

选择数据库
> use course;

创建数据表，

[基础]请根据此 sql 表写出对应的kotlin data class
[提高]请根据以下 sql 脚本，结合 xmind 创建出新的数据表

```sql
create table classes(
	cid int not null primary key,
	cname varchar(64) not null,
	cstudents varchar(255) not null
)

create table students(
	sid varchar(64) not null primary key,
	sname varchar(64) not null,
	spassword varchar(64) not null,
	savatar varchar(255) not null,
	stoken int not null,
	sgithub varchar(255),
	shomework varchar(255),
	sequipments varchar(1023),
	sprops varchar(1023),
	scommodities varchar(1023)
)

create table equipments(
	eid int not null primary key auto_increment,
	ename varchar(127) not null,
	eimage varchar(255) not null,
	eprice double not null,
	eamount int not null,
	edetails varchar(255) not null
) auto_increment=1

create table props(
	pid int not null primary key auto_increment,
	pname varchar(127) not null,
	pimage varchar(255) not null,
	pprice double not null,
	pamount int not null,
	pdetails varchar(255) not null
) auto_increment=1

create table majors(
	mid int not null primary key,
	mname varchar(128) not null
)
```

