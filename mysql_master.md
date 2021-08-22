## 1.初始SQL
```mysql

mysql -u root -p123456   -- 连接数据库
--------------------------------------
--所有语句都使用 ; 结尾
show databases;  -- 查看所有的数据库

mysql> use school;  -- 切换数据库  use 数据库名
Database changed

show tables;  -- 查看数据库中所有的表
describe student;  -- 显示数据库中的所有表的信息

create database westors;  -- 创建一个数据库

exit;   -- 退出连接

-- 单行注释（SQL本来的注释）
/*（多行注释）
123
*/
```
## 2.操作数据库
### 2.1操作数据库
- 1.创建数据库
```SQL
CREATE DATABASE IF NOT EXISTS westors
```
- 2.删除数据库
```SQL
DROP DATABASE IF EXISTS westors
```
- 3.查看数据库
```SQL
SHOW DATABASES
```
### 2.2 数据库的列类型  

## 3. 设计数据库的步骤
- 收集信息，分析需求
  - 用户表（用户登录注销，用户的个人信息）
  - 




















