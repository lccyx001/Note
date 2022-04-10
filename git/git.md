# 搭建git代码仓库

## 创建git用户

useradd git
passwd git

输入密码: git
确认密码: git

## 创建代码仓库

创建代码仓库目录 /home/git/

创建代码仓库  mkdir A.git

```.json
cd A.git
git init --bare

chown -R git:git /data/repositories
```

## clone代码到本地

```


git clone ssh://git@116.196.83.187:63212/home/git/wuliao.git

```
