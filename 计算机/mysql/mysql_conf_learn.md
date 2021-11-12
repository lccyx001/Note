<!-- https://www.cnblogs.com/wyy123/p/6092976.html -->
# mysql 安装，配置

## 卸载mysql

- 停止mysql进程 kill pid
- find / -name mysql
- yum remove mysql

## mysql8 安装

- yum install mysql
- 从mysql官网下载rpm包 yum install -y rpm包
- yum install mysql-community-server

- systemctl start mysqld.service
- systemctl status mysqld.service
- systemctl enable mysqld.service
- cat /var/log/mysqld.log 找到对应密码
- mysql -uroot -p 输入密码
- ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'YourPassword'; 新密码需要设置高强度密码，否则需要修改mysql密码强度设置
- select host,user from mysql.user; 查看用户权限
- update user set host='%' where user = 'root';  设置远程访问
或者
- grant all privileges on *.* to 'root'@'%'; 赋权
- flush privileges

## 修改mysql密码强度

- set global validate_password.policy=0;
- set global validate_password.length=4;

## 修改mysql配置文件

修改前停止mysqld进程
mysql配置文件默认位置 /etc/mysql/my.cnf

- mkdir /data/mysql
- cp -R /var/lib/mysql /data/mysql 这一步把原my.cnf中datadir目录下所有文件拷贝到新目录
- chown mysql:mysql -R /data/mysql/

修改数据存储位置: datadir="/data/mysql" 这里主要修改mysqld的配置
修改完成之后重启mysqld

查看修改结果
show variables like '%dir%';
