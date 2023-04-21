# Date format conversion

- `DATE` 함수 변환

  ```sql
  -- DAY

  SELECT NAME, EXP, DAY(EXP)
  FROM PRODUCT_INFO;
  +-------------+---------------------+----------+
  | NAME        | EXP                 | DAY(EXP) |
  +-------------+---------------------+----------+
  | CocaCola    | 2025-05-05 05:05:05 |        5 |
  | Sprite      | 2025-01-31 23:00:10 |       31 |
  | PocariSweat | 2024-12-28 01:20:28 |       28 |
  | Pepsi       | 2026-11-28 09:09:09 |       28 |
  | Monster     | 2023-04-21 15:11:04 |       21 |
  +-------------+---------------------+----------+
  ```
  ```sql
  -- DAYNAME

  SELECT NAME, MFG_DATE, DAYNAME(MFG_DATE)
  FROM PRODUCT_INFO;
  +-------------+------------+-------------------+
  | NAME        | MFG_DATE   | DAYNAME(MFG_DATE) |
  +-------------+------------+-------------------+
  | CocaCola    | 2023-03-03 | Friday            |
  | Sprite      | 2023-04-24 | Monday            |
  | PocariSweat | 2023-01-01 | Sunday            |
  | Pepsi       | 2023-06-06 | Tuesday           |
  | Monster     | 2023-04-21 | Friday            |
  +-------------+------------+-------------------+
  ```

<br>

- `TIME` 함수 변환

  ```sql
  -- HOUR

  SELECT NAME, MFG_TIME, HOUR(MFG_TIME)
  FROM PRODUCT_INFO;
  +-------------+----------+----------------+
  | NAME        | MFG_TIME | HOUR(MFG_TIME) |
  +-------------+----------+----------------+
  | CocaCola    | 03:03:03 |              3 |
  | Sprite      | 22:22:22 |             22 |
  | PocariSweat | 00:00:05 |              0 |
  | Pepsi       | 06:06:06 |              6 |
  | Monster     | 15:11:04 |             15 |
  +-------------+----------+----------------+
  ```
  ```sql
  -- MINUTE

  SELECT NAME, MFG_TIME, MINUTE(MFG_TIME)
  FROM PRODUCT_INFO;
  +-------------+----------+------------------+
  | NAME        | MFG_TIME | MINUTE(MFG_TIME) |
  +-------------+----------+------------------+
  | CocaCola    | 03:03:03 |                3 |
  | Sprite      | 22:22:22 |               22 |
  | PocariSweat | 00:00:05 |                0 |
  | Pepsi       | 06:06:06 |                6 |
  | Monster     | 15:11:04 |               11 |
  +-------------+----------+------------------+
  ```

<br>

- `DATETIME` 변환

  ```sql
  -- DAYNAME

  SELECT NAME, EXP, DAYNAME(EXP)
  FROM PRODUCT_INFO;
  +-------------+---------------------+--------------+
  | NAME        | EXP                 | DAYNAME(EXP) |
  +-------------+---------------------+--------------+
  | CocaCola    | 2025-05-05 05:05:05 | Monday       |
  | Sprite      | 2025-01-31 23:00:10 | Friday       |
  | PocariSweat | 2024-12-28 01:20:28 | Saturday     |
  | Pepsi       | 2026-11-28 09:09:09 | Saturday     |
  | Monster     | 2023-04-21 15:11:04 | Friday       |
  +-------------+---------------------+--------------+
  ```
  ```sql
  -- MONTHNAME

  SELECT NAME, EXP, MONTHNAME(EXP) FROM PRODUCT_INFO;
  +-------------+---------------------+----------------+
  | NAME        | EXP                 | MONTHNAME(EXP) |
  +-------------+---------------------+----------------+
  | CocaCola    | 2025-05-05 05:05:05 | May            |
  | Sprite      | 2025-01-31 23:00:10 | January        |
  | PocariSweat | 2024-12-28 01:20:28 | December       |
  | Pepsi       | 2026-11-28 09:09:09 | November       |
  | Monster     | 2023-04-21 15:11:04 | April          |
  +-------------+---------------------+----------------+
  ```

<br>

- `DATE_FORMAT`
  ```sql
  SELECT NAME,
         DATE_FORMAT(EXP, "%W %M %Y") AS "EXP: DATE FORMAT"
  FROM PRODUCT_INFO;
  +-------------+------------------------+
  | NAME        | EXP: DATE FORMAT       |
  +-------------+------------------------+
  | CocaCola    | Monday May 2025        |
  | Sprite      | Friday January 2025    |
  | PocariSweat | Saturday December 2024 |
  | Pepsi       | Saturday November 2026 |
  | Monster     | Friday April 2023      |
  +-------------+------------------------+
  ```
  ```sql
  SELECT
  CONCAT("The EXP date of thie ", NAME, ": ", DATE_FORMAT(EXP, "%m/%d/%Y at %h:%m"))
  AS "PRODUCT EXP INFO"
  FROM PRODUCT_INFO;
  +-------------------------------------------------------+
  | PRODUCT EXP INFO                                      |
  +-------------------------------------------------------+
  | The EXP date of thie CocaCola: 05/05/2025 at 05:05    |
  | The EXP date of thie Sprite: 01/31/2025 at 11:01      |
  | The EXP date of thie PocariSweat: 12/28/2024 at 01:12 |
  | The EXP date of thie Pepsi: 11/28/2026 at 09:11       |
  | The EXP date of thie Monster: 04/21/2023 at 03:04     |
  +-------------------------------------------------------+
  ```
  ```sql
  SELECT DATE_FORMAT(NOW(), "%M %D at %h:%i")
  AS "TODAY IS ...";
  +---------------------+
  | TODAY IS ...        |
  +---------------------+
  | April 21st at 03:22 |
  +---------------------+
  ```
