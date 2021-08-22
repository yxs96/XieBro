### SQL时间戳的使用
- 1.基本概念  
  - 时间戳：数据库中自动生成的唯一二进制数字，与时间和日期无关的，通常用作给表、行加版本戳的机制。存储大小为8个字节。

- 2.时间戳的作用
  - 在控制并发时起到作用

- 3.时间戳的应用
  - 主要是记录该行的最后修改时间戳，且该时间戳是不可以转换为时间的，只能标记该行修改了，通过where条件进行限定

### 具体函数
- 1.FROM_UNIXTIME()时间戳转换函数
  - 语法：FROM_UNIXTIME(unix_timestamp,format)
  - 作用：将MYSQL中以INT(11)存储的时间以"YYYY-MM-DD"格式来显示
- 2.SQL limit关键字
  - 格式：limit **偏移量**  **所取行数**  
  - ```SQL select * from employees order by hire_date desc limit 2,1;```
    - 如果只给一个参数，表示返回最大的记录行数目  
        ```SQL SELECT * FROM table LIMIT 5; //检索前 5 个记录行```
    - 如果给定两个参数，第一个参数指定第一个返回记录行的偏移量，第二个参数指定返回记录行的最大数目  
        ```SELECT * FROM table LIMIT 5,10; //检索记录行6-15 引用块内容```  
        limit m,n表示从第m条记录开始，往后取n条记录（第一条记录是从0开始的，第2条记录是从1开始的，一次类推
- 3. COUNT、Group By



