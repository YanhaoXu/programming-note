# Mysql笔记

## 1. MySQL的安装和配置

+ docker 安装 mysql 8 版本

```shell
# docker 中下载 mysql
docker 安装 mysql 8 版本

#启动
docker run -d ^
 --name mysql8 ^
 -p 3306:3306 ^
 --privileged=true ^
 -e MYSQL_ROOT_PASSWORD="123456" ^
 -e character-set-server=utf-8 ^
 -e collation-server=utf8_general_ci ^
 -v=D:/DevOps/docker/volume/database/mysql/data/mysql:/var/lib/mysql ^
 -v=D:/DevOps/docker/volume/database/mysql/logs:/logs ^
 -v=D:/DevOps/docker/volume/database/mysql/conf/my.cnf:/etc/mysql/my.cnf ^
 -v=D:/DevOps/docker/volume/database/mysql/lib/mysql-files:/var/lib/mysql-files ^
 mysql

#进入容器
docker exec -it mysql8 bash
```

+ 准备的目录和文件

> D:\DevOps\docker\volume\database\mysql\lib\mysql-files

> D:\DevOps\docker\volume\database\mysql\conf\my.cnf

```ini
[mysqld]
secure_file_priv=/var/lib/mysql
```

## 2. MySQL用户管理

+ 快速配置

```shell
#登录mysql
mysql -u root -p

ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';

#添加远程登录用户
CREATE USER 'testdb'@'%' IDENTIFIED WITH mysql_native_password BY '123456';
CREATE USER 'testdb'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';
GRANT ALL PRIVILEGES ON *.* TO 'testdb'@'%';
GRANT ALL PRIVILEGES ON *.* TO 'testdb'@'localhost';


create schema test;

```

## 3. MySQL数据库的基本操作
```sql
# 创建数据库（CREATE DATABASE语句）
CREATE DATABASE IF NOT EXISTS test_db;

# 查看 test_db 数据库的定义声明
SHOW CREATE DATABASE test_db;

# 修改数据库（ALTER DATABASE语句）
ALTER DATABASE test_db
DEFAULT CHARACTER SET gb2312
DEFAULT COLLATE gb2312_chinese_ci;

# 删除数据库（DROP DATABASE语句）
DROP DATABASE IF EXISTS test_db;

# 选择数据库（MySQL USE语句）
USE test_db;

```
## 4. MySQL数据表的基本操作

```sql
# 在指定的数据库中创建表
# 创建员工表 tb_emp1
create table if not exists test_db.tb_emp1
(
    id     INT(11),
    name   VARCHAR(25),
    deptId INT(11),
    salary FLOAT
);

# 查看数据表是否创建成功
SHOW TABLES;

# MySQL查看表结构命令
# DESCRIBE：以表格的形式展示表结构
DESCRIBE <表名>;
DESC <表名>;
# SHOW CREATE TABLE：以SQL语句的形式展示表结构
SHOW CREATE TABLE <表名>;

# MySQL数据表添加字段
# 新建 student 数据表
drop table if exists test_db.student;
create table if not exists test_db.student
(
    id   int(4),
    name varchar(20),
    sex  char(1)
);

# 使用 ALTER TABLE 语句添加一个 INT 类型的字段 age
alter table student add age int(4);

# MySQL修改/删除字段
# 修改字段名称










# 修改数据表
# 修改表名
ALTER TABLE student RENAME TO tb_students_info;
```