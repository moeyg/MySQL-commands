# DATE & TIME & DATETIME

- `DATE` : 날짜를 나타내는 데이터 타입으로, `YYYY-MM-DD` 형식으로 저장<br>
- `TIME` : 시간을 나타내는 데이터 타입으로, `HH:MM:SS` 형식으로 저장<br>
- `DATETIME` : 날짜와 시간을 모두 포함하는 데이터 타입으로, `YYYY-MM-DD HH:MM:SS` 형식으로 저장<br>

  ```sql
  -- CREATE TABLE

  CREATE TABLE PRODUCT_INFO
  (
      NAME VARCHAR(25),
      PRODUCTION_DATE DATE,
      PRODUCTION_TIME TIME,
      EXPIRATION_DT DATETIME
  );
  ```
  ```sql
  -- INSERT datas

  INSERT INTO PRODUCT_INFO (NAME, PRODUCTION_DATE, PRODUCTION_TIME, EXPIRATION_DT)
  VALUES ("CocaCola", "2023-03-03", "03:03:03", "2025-05-05 05:05:05"),
         ("Sprite", "2023-04-24", "22:22:22", "2025-01-31 23:00:10"),
         ("PocariSweat", "2023-01-01", "00:00:05", "2024-12-28 01:20:28"),
         ("Pepsi", "2023-06-06", "06:06:06", "2026-11-28 09:09:09");
  ```
  ```sql
  -- Result

  SELECT * FROM PRODUCT_INFO;
  +-------------+-----------------+-----------------+---------------------+
  | NAME        | PRODUCTION_DATE | PRODUCTION_TIME | EXPIRATION_DT       |
  +-------------+-----------------+-----------------+---------------------+
  | CocaCola    | 2023-03-03      | 03:03:03        | 2025-05-05 05:05:05 |
  | Sprite      | 2023-04-24      | 22:22:22        | 2025-01-31 23:00:10 |
  | PocariSweat | 2023-01-01      | 00:00:05        | 2024-12-28 01:20:28 |
  | Pepsi       | 2023-06-06      | 06:06:06        | 2026-11-28 09:09:09 |
  +-------------+-----------------+-----------------+---------------------+
  ```
