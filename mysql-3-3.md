## 连接数据库
* cmd->输入命令mysql -uroot -p -> 回车 -> 输入密码123
## 数据库基本操作
* mysql> CREATE DATABASE PRJ;  #创建数据库
Query OK, 1 row affected (0.11 sec)

mysql> show databases;  #显示所有数据库
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| prj                |
| sys                |
+--------------------+
5 rows in set (0.19 sec)

mysql> show tables;   #显示所有表
ERROR 1046 (3D000): No database selected
mysql> use prj  #选择数据库
Database changed
mysql> show tables;  #显示所有表
Empty set (0.04 sec)
mysql> CREATE TABLE Student  #创建一个Student表
    -> (Sno CHAR(9) PRIMARY KEY,
    -> Sname CHAR(20) UNIQUE,
    -> Ssex CHAR(2),
    -> Sage SMALLINT,
    -> Sdept CHAR(20)
    -> );
Query OK, 0 rows affected (0.54 sec)

mysql> show tables;  #显示所有表
+---------------+
| Tables_in_prj |
+---------------+
| student       |
+---------------+
1 row in set (0.00 sec)
mysql> ALTER TABLE Student ADD S_entrance DATE;  #向Student表添加“入学时间”列 数据类型为日期型
Query OK, 0 rows affected (0.63 sec)
Records: 0  Duplicates: 0  Warnings: 0
mysql> DROP TABLE student CASCADE;  #删除Student表的所有相关依赖对象（如视图）
Query OK, 0 rows affected (0.17 sec)
