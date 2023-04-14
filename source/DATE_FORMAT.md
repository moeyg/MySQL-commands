# Date format conversion

- `DATE` 함수 변환

  ```sql
  -- DAY

  mysql> SELECT name, birthDATE, DAY(birthDATE)
      -> FROM birth;
  +--------+------------+----------------+
  | name   | birthDATE  | DAY(birthDATE) |
  +--------+------------+----------------+
  | Thomas | 2020-02-02 |              2 |
  | Ron    | 2021-07-12 |             12 |
  | Woody  | 2022-10-10 |             10 |
  | Drew   | 2023-04-14 |             14 |
  +--------+------------+----------------+
  4 rows in set (0.00 sec)

  -- DAYNAME

  mysql> SELECT name, birthDATE, DAYNAME(birthDATE) FROM birth;
  +--------+------------+--------------------+
  | name   | birthDATE  | DAYNAME(birthDATE) |
  +--------+------------+--------------------+
  | Thomas | 2020-02-02 | Sunday             |
  | Ron    | 2021-07-12 | Monday             |
  | Woody  | 2022-10-10 | Monday             |
  | Drew   | 2023-04-14 | Friday             |
  +--------+------------+--------------------+
  4 rows in set (0.00 sec)
  ```

<br>

- `TIME` 함수 변환

  ```sql
  -- HOUR

  mysql> SELECT name, birthTIME, HOUR(birthTIME) FROM birth;
  +--------+-----------+-----------------+
  | name   | birthTIME | HOUR(birthTIME) |
  +--------+-----------+-----------------+
  | Thomas | 10:00:01  |              10 |
  | Ron    | 08:08:08  |               8 |
  | Woody  | 22:23:24  |              22 |
  | Drew   | 21:46:05  |              21 |
  +--------+-----------+-----------------+
  4 rows in set (0.00 sec)

  -- MINUTE

  mysql> SELECT name, birthTIME, MINUTE(birthTIME) FROM birth;
  +--------+-----------+-------------------+
  | name   | birthTIME | MINUTE(birthTIME) |
  +--------+-----------+-------------------+
  | Thomas | 10:00:01  |                 0 |
  | Ron    | 08:08:08  |                 8 |
  | Woody  | 22:23:24  |                23 |
  | Drew   | 21:46:05  |                46 |
  +--------+-----------+-------------------+
  4 rows in set (0.00 sec)
  ```

<br>

- `DATETIME` 변환

  ```sql
  -- DAYNAME

  mysql> SELECT name, birthDT, DAYNAME(birthDT) FROM birth;
  +--------+---------------------+------------------+
  | name   | birthDT             | DAYNAME(birthDT) |
  +--------+---------------------+------------------+
  | Thomas | 2020-02-02 10:00:01 | Sunday           |
  | Ron    | 2021-07-12 08:08:08 | Monday           |
  | Woody  | 2022-10-10 22:23:24 | Monday           |
  | Drew   | 2023-04-14 21:46:05 | Friday           |
  +--------+---------------------+------------------+
  4 rows in set (0.00 sec)

  -- MONTHNAME

  mysql> SELECT name, birthDT, MONTHNAME(birthDT) FROM birth;
  +--------+---------------------+--------------------+
  | name   | birthDT             | MONTHNAME(birthDT) |
  +--------+---------------------+--------------------+
  | Thomas | 2020-02-02 10:00:01 | February           |
  | Ron    | 2021-07-12 08:08:08 | July               |
  | Woody  | 2022-10-10 22:23:24 | October            |
  | Drew   | 2023-04-14 21:46:05 | April              |
  +--------+---------------------+--------------------+
  4 rows in set (0.01 sec)

  -- SECOND

  mysql> SELECT name, birthDT, SECOND(birthDT) FROM birth;
  +--------+---------------------+-----------------+
  | name   | birthDT             | SECOND(birthDT) |
  +--------+---------------------+-----------------+
  | Thomas | 2020-02-02 10:00:01 |               1 |
  | Ron    | 2021-07-12 08:08:08 |               8 |
  | Woody  | 2022-10-10 22:23:24 |              24 |
  | Drew   | 2023-04-14 21:46:05 |               5 |
  +--------+---------------------+-----------------+
  4 rows in set (0.01 sec)
  ```

<br>

- `DATE_FORMAT`
  ```sql
  mysql> SELECT name,
      ->        DATE_FORMAT(birthDT, "%W %M %Y") AS "DATE"
      -> FROM birth;
  +--------+----------------------+
  | name   | DATE                 |
  +--------+----------------------+
  | Thomas | Sunday February 2020 |
  | Ron    | Monday July 2021     |
  | Woody  | Monday October 2022  |
  | Drew   | Friday April 2023    |
  +--------+----------------------+
  4 rows in set (0.00 sec)
  ```
  ```sql
  mysql> SELECT
      -> CONCAT(name,
      ->       " was born when ",
      ->       DATE_FORMAT(birthDT, "%m/%d/%Y at %h:%m")) AS "birthday reminder"
      -> FROM birth;
  +------------------------------------------+
  | birthday reminder                        |
  +------------------------------------------+
  | Thomas was born when 02/02/2020 at 10:02 |
  | Ron was born when 07/12/2021 at 08:07    |
  | Woody was born when 10/10/2022 at 10:10  |
  | Drew was born when 04/14/2023 at 09:04   |
  +------------------------------------------+
  4 rows in set (0.00 sec)
  ```
  ```sql
  mysql> SELECT DATE_FORMAT(NOW(), "%M %D at %h:%i");
  +--------------------------------------+
  | DATE_FORMAT(NOW(), "%M %D at %h:%i") |
  +--------------------------------------+
  | April 15th at 12:14                  |
  +--------------------------------------+
  1 row in set (0.00 sec)
  ```
