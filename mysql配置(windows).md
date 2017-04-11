# mysql的安装配置

## 下载
去[mysql官网](https://dev.mysql.com/downloads/mysql/)下载免安装版，我的版本为5.7.17

## 环境变量
此电脑->属性->高级系统设置->环境变量->Path中添加环境变量（如我把mysql解压到d盘，对应就添加D:\mysql-5.7.17-winx64\bin）

## 创建my.ini
在解压的D:\mysql-5.7.17-winx64中新建my.ini（注意要用ANSI编码，可用记事本编辑），内容如下：

[mysql]
#设置mysql客户端默认字符集
default-character-set=utf8 
[mysqld]
#设置3306端口
port = 3306 
#设置mysql的安装目录
basedir=D:\mysql-5.7.17-winx64
#设置mysql数据库的数据的存放目录
datadir=D:\mysql-5.7.17-winx64\data
#允许最大连接数
max_connections=200
#服务端使用的字符集默认为8比特编码的latin1字符集
character-set-server=utf8
#创建新表时将使用的默认存储引擎
default-storage-engine=INNODB

## 安装mysql
* 以管理员身份运行cmd
cd D:\mysql-5.7.17-winx64\bin
* 命令1：mysqld --initialize   #直接初始化mysql，生成data文件夹中的文件。
* 命令2：mysqld -install       #安装mysql
* 命令3：net start mysql       #启动服务器
* 如果输入命令2后出现"The service already exists!"，输入命令sc delete mysql 删除已有数据库。
当出现"[SC] DeleteService 成功"后，重新输入命令2，则会出现"Service successfully installed."
这时已成功安装数据库。

## 登录mysql
* 输入命令： mysql -uroot -p密码 就可以登录，当不知道密码时，用下面的方法就可以重设密码
* 编辑解压目录下的 my.ini文件，在[mysqld]这个条目下加入
skip-grant-tables
* 保存退出后重启mysql
进入cmd
输入命令：net stop mysql    #停止
输入命令：net start mysql   #启动
这时在cmd里面输入mysql -u root -p不用密码可以登录。出现password：时，直接回车可以进入mysql。

## 更改密码
* 进入mysql 数据库：
mysql> use mysql;
显示：
Database changed
* 给root用户设置新密码，在命令行输入：
mysql> update user set authentication_string=password('123txm') where user='root' and Host = 'localhost';
显示：
Query OK, 1 rows affected (0.01 sec)
Rows matched: 1 Changed: 1 Warnings: 0
* 刷新数据库
mysql> flush privileges;
显示：
Query OK, 0 rows affected (0.00 sec)
* 退出mysql
mysql> quit
显示
Bye
改好之后，再修改一下my.ini这个文件，把之前加入的"skip-grant-tables"删除，保存退出再重启mysql就可以了。

## 完善
* 修改完毕。重启mysql服务。
* 输入命令：mysql -uroot -p123txm    #登录mysql
* 输入命令：alter user 'root'@'localhost' identified by '123';
* 输入命令：mysql>quit;
* 以后可直接在命令行输入mysql -uroot -p
Enter password:123
就能登录mysql了。

## 参考
* [windows下mysql配置（第一次）](http://www.cnblogs.com/by330326/p/5608290.html)
* [Windows上安装MySQL](http://blog.csdn.net/u013235478/article/details/50623693)
* [在服务器上无法启动mysql服务 错误193 求高手指点](http://www.debugease.com/mysql/119481.html)
