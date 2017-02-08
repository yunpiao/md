---
title: Postgresql 安装 配置

---
## 配置
sudo adduser dbuser

sudo su - postgres

psql

\password postgres

CREATE USER dbuser WITH PASSWORD 'password';

CREATE DATABASE exampledb OWNER dbuser;

GRANT ALL PRIVILEGES ON DATABASE exampledb to dbuser;

## 远程访问

vi /etc/postgresql/8.4/main/pg_hba.conf  
添加
host    all         all         192.168.98.0/24       md5
 
如下：
 
找到 listen_addresses = 'localhost' 这一行，将它改为：

 listen_addresses = '*'