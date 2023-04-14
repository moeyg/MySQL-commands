# DATE & TIME & DATETIME

- `DATE` : 날짜를 나타내는 데이터 타입으로, `YYYY-MM-DD` 형식으로 저장<br>
- `TIME` : 시간을 나타내는 데이터 타입으로, `HH:MM:SS` 형식으로 저장<br>
- `DATETIME` : 날짜와 시간을 모두 포함하는 데이터 타입으로, `YYYY-MM-DD HH:MM:SS` 형식으로 저장<br>

  ```sql
  -- CREATE TABLE

  mysql> CREATE TABLE birth
      -> (
      ->      name VARCHAR(25),
      ->      birthDATE DATE,
      ->      birthTIME TIME,
      ->      birthDT DATETIME
      -> );
  Query OK, 0 rows affected (0.01 sec)

  -- INSERT datas

  mysql> INSERT INTO birth(name, birthDATE, birthTIME, birthDT)
      -> VALUES ("Thomas", "2020-02-02", "10:00:01", "2020-02-02 10:00:01"),
      ->        ("Ron", "2021-07-12", "08:08:08", "2021-07-12 08:08:08"),
      ->        ("Woody", "2022-10-10", "22:23:24", "2022-10-10 22:23:24");
  Query OK, 3 rows affected (0.00 sec)
  Records: 3  Duplicates: 0  Warnings: 0

  -- Result

  mysql> SELECT * FROM birth;
  +--------+------------+-----------+---------------------+
  | name   | birthDATE  | birthTIME | birthDT             |
  +--------+------------+-----------+---------------------+
  | Thomas | 2020-02-02 | 10:00:01  | 2020-02-02 10:00:01 |
  | Ron    | 2021-07-12 | 08:08:08  | 2021-07-12 08:08:08 |
  | Woody  | 2022-10-10 | 22:23:24  | 2022-10-10 22:23:24 |
  +--------+------------+-----------+---------------------+
  3 rows in set (0.00 sec)
  ```
