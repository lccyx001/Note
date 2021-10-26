## mac 安装启动mysql

```sh
brew install mysql

brew services start mysql  // run background

mysql.server start

mysql_secure_installation //设置密码等

mysql -u root -p 
```

```sh
show databases;

```

- 报错1449 The user specified as a definer ('mysql.infoschema'@'localhost') does not exist

解决办法

```sql
mysql> create user 'mysql.infoschema'@'%' identified by '密码';
Query OK, 0 rows affected (0.01 sec)
mysql> grant all privileges on *.* to 'mysql.infoschema'@'%';
Query OK, 0 rows affected (0.01 sec)
mysql> flush privileges;
Query OK, 0 rows affected (0.01 sec)
```

## 密码忘记重制方法 （适用8.0版本）

```sql
mysqld --console --skip-grant-tables

mysql -u root -p

use mysql; 
update user set authentication_string='' where user='root';
update user set plugin="mysql_native_password";
flush privileges;
mysqladmin -u root -p password
会提示password, 直接enter
提示输入新密码，输入后enter
提示输入确认密码，输入后enter;
```