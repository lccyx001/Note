# 使用dock启动mysql容器

## 1

```shell
启动mysql容器

docker run --name mysql-latest -v E:/Docker/mysql/mysql-latest/custom:/etc/mysql/conf.d -v E:/Docker/mysql/mysql-latest/data:/var/lib/mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 -d mysql:latest


```

```shell
命令解释

--name mysql-latest
▲ --name xxxx 為容器名稱，可自定義。

-v D:/Docker/mysql/mysql-latest/custom:/etc/mysql/conf.d
▲ -v 為放置鏡像檔的路徑(本機)，與要鏡像出來的檔案(容器內)，以「:」分隔。

-p 3306:3306
▲ -p 將本機內的port關聯至容器內的port。

-e MYSQL_ROOT_PASSWORD=123456
▲ -e 容器環境參數變數設定。

-d mysql:latest
▲ -d 讓Container在背景執行。
```

## 2

打开容器，在docker终端中输入指令

```shell
mysql -u root -p
```

## 3

新建一个用户test 密码为test123

```shell
CREATE USER 'test'@'%' IDENTIFIED BY 'test123';
GRANT ALL ON *.* TO 'test'@'%'  WITH GRANT OPTION;
ALTER USER 'test'@'%' IDENTIFIED WITH mysql_native_password BY 'test123';
```

## 4 测试连接

