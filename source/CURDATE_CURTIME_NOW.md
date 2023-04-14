# CURDATE & CURTIME & NOW

- `CURDATE` : 현재 날짜를 YYYY-MM-DD 형식의 문자열로 반환<br>
- `CURTIME` : 현재 시간을 HH:MM:SS 형식의 문자열로 반환<br>
- `NOW` : 현재 날짜와 시간을 YYYY-MM-DD HH:MM:SS 형식의 문자열로 반환<br>

  ```sql
  -- INSERT datas

  mysql> INSERT INTO birth(name, birthDATE, birthTIME, birthDT)
      -> VALUES ("Drew", CURDATE(), CURTIME(), NOW());
  Query OK, 1 row affected (0.00 sec)

  -- Result

  mysql> SELECT * FROM birth;
  +--------+------------+-----------+---------------------+
  | name   | birthDATE  | birthTIME | birthDT             |
  +--------+------------+-----------+---------------------+
  | Thomas | 2020-02-02 | 10:00:01  | 2020-02-02 10:00:01 |
  | Ron    | 2021-07-12 | 08:08:08  | 2021-07-12 08:08:08 |
  | Woody  | 2022-10-10 | 22:23:24  | 2022-10-10 22:23:24 |
  | Drew   | 2023-04-14 | 21:46:05  | 2023-04-14 21:46:05 |
  +--------+------------+-----------+---------------------+
  4 rows in set (0.00 sec)
  ```
