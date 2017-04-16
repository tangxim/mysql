## 插入数据
* **INSERT INTO 表名 (列名1,……,列名n) VALUES(数据1,……,数据n);**
  
  mysql> INSERT INTO Student
      
      -> (Sno,Sname,Ssex,Sage,Sdept)
      
      -> VALUES('201215121','李勇','男',20,'CS');
  
  Query OK, 1 row affected (0.12 sec)
## 单表查询
* **查询所有数据信息**
  
  **SELECT * FROM 表名;**
  mysql> SELECT * FROM Student;
  
  +-----------+--------+------+------+-------+
  
  | Sno       | Sname  | Ssex | Sage | Sdept |
  
  +-----------+--------+------+------+-------+
  
  | 201215121 | 李勇   | 男   |   20 | CS    |
  
  +-----------+--------+------+------+-------+
  
  1 row in set (0.05 sec)
* **查询特定列**
  
  **SELECT 列名1,……,列名n FROM 表名;**
  
  mysql> SELECT Sno,Sname FROM Student;
  
  +-----------+--------+
  
  | Sno       | Sname  |
  
  +-----------+--------+
  
  | 201215122 | 刘晨   |
  
  | 201215125 | 张立   |
  
  | 201215121 | 李勇   |
  
  | 201215123 | 王敏   |
  
  +-----------+--------+
  
  4 rows in set (0.05 sec)
* **查询经过计算的值**
  
  **SELECT 算术表达式 FROM 表名;**
  
  mysql> SELECT Sname,2017-Sage FROM Student;
  
  +--------+-----------+
  
  | Sname  | 2017-Sage |
  
  +--------+-----------+
  
  | 李勇   |      1997 |
  
  | 刘晨   |      1998 |
  
  | 王敏   |      1999 |
  
  | 张立   |      1998 |
  
  +--------+-----------+
  
  4 rows in set (0.05 sec)
* **起别名**
  
  mysql> SELECT Sname,'Year of Birth:',2017-Sage,LOWER(Sdept) FROM Student;
  
  +--------+----------------+-----------+--------------+
  
  | Sname  | Year of Birth: | 2017-Sage | LOWER(Sdept) |
  
  +--------+----------------+-----------+--------------+
  
  | 李勇   | Year of Birth: |      1997 | cs           |
  
  | 刘晨   | Year of Birth: |      1998 | cs           |
  
  | 王敏   | Year of Birth: |      1999 | ma           |
  
  | 张立   | Year of Birth: |      1998 | is           |
  
  +--------+----------------+-----------+--------------+
  
  4 rows in set (0.07 sec)

  
  mysql> SELECT Sname NAME,'Year of Birth:' BIRTH,2017-Sage BIRTHDAY,LOWER(Sdept) DEPARTMENT FROM Student;
  
  +--------+----------------+----------+------------+
  
  | NAME   | BIRTH          | BIRTHDAY | DEPARTMENT |
  
  +--------+----------------+----------+------------+
  
  | 李勇   | Year of Birth: |     1997 | cs         |
  
  | 刘晨   | Year of Birth: |     1998 | cs         |
  
  | 王敏   | Year of Birth: |     1999 | ma         |
  
  | 张立   | Year of Birth: |     1998 | is         |
  
  +--------+----------------+----------+------------+
  
  4 rows in set (0.00 sec)
## Student表数据
  
  mysql> INSERT INTO Student
      
      -> (Sno,Sname,Ssex,Sage,Sdept)
      
      -> VALUES('201215121','李勇','男',20,'CS');
  
  mysql> INSERT INTO Student
      
      -> (Sno,Sname,Ssex,Sage,Sdept)
      
      -> VALUES('201215122','刘晨','女',19,'CS');

  
  mysql> INSERT INTO Student
      
      -> (Sno,Sname,Ssex,Sage,Sdept)
      
      -> VALUES('201215123','王敏','女',18,'MA');

  
  mysql> INSERT INTO Student
      
      -> (Sno,Sname,Ssex,Sage,Sdept)
      
      -> VALUES('201215125','张立','男',19,'IS');
## Course表数据
mysql> INSERT INTO Course
    -> (Cno,Cname,Ccredit)
    -> VALUES('1','数据库',4);

mysql> INSERT INTO Course
    -> (Cno,Cname,Ccredit)
    -> VALUES('2','数学',2);

mysql> INSERT INTO Course
    -> (Cno,Cname,Ccredit)
    -> VALUES('3','信息系统',4);

mysql> INSERT INTO Course
    -> (Cno,Cname,Ccredit)
    -> VALUES('4','操作系统',3);

mysql> INSERT INTO Course
    -> (Cno,Cname,Ccredit)
    -> VALUES('5','数据结构',4);

mysql> INSERT INTO Course
    -> (Cno,Cname,Ccredit)
    -> VALUES('6','数据处理',2);

mysql> INSERT INTO Course
    -> (Cno,Cname,Ccredit)
    -> VALUES('7','PASCAL语言',4);
## SC表数据
mysql> INSERT INTO SC
    -> (Sno,Cno,Grade)
    -> VALUES('201215121','1',92);

mysql> INSERT INTO SC
    -> (Sno,Cno,Grade)
    -> VALUES('201215121','2',85);

mysql> INSERT INTO SC
    -> (Sno,Cno,Grade)
    -> VALUES('201215121','3',88);

mysql> INSERT INTO SC
    -> (Sno,Cno,Grade)
    -> VALUES('201215122','2',90);

mysql> INSERT INTO SC
    -> (Sno,Cno,Grade)
    -> VALUES('201215122','3',80);
## Course表外码Cpno数据
mysql> UPDATE Course
    -> SET Cpno='5'
    -> WHERE Cno='1';

mysql> UPDATE Course
    -> SET Cpno='1'
    -> WHERE Cno='3';

mysql> UPDATE Course
    -> SET Cpno='6'
    -> WHERE Cno='4';

mysql> UPDATE Course
    -> SET Cpno='7'
    -> WHERE Cno='5';

mysql> UPDATE Course
    -> SET Cpno='6'
    -> WHERE Cno='7';
