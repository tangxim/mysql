## 插入数据
* **INSERT INTO 表名 (列名1,……,列名n) VALUES(数据1,……,数据n);**
  
  mysql> INSERT INTO Student
      
      -> (Sno,Sname,Ssex,Sage,Sdept)
      
      -> VALUES('201215121','李勇','男',20,'CS');
  
  Query OK, 1 row affected (0.12 sec)
## 查询数据
* **查询所有数据信息**
  
  mysql> **SELECT * FROM Student;**
  
  +-----------+--------+------+------+-------+
  
  | Sno       | Sname  | Ssex | Sage | Sdept |
  
  +-----------+--------+------+------+-------+
  
  | 201215121 | 李勇   | 男   |   20 | CS    |
  
  +-----------+--------+------+------+-------+
  
  1 row in set (0.05 sec)
* **查询特定信息**
