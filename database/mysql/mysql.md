# Mysql笔记

## 一、MySQL的安装和配置

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

## 二、MySQL用户管理

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
```

