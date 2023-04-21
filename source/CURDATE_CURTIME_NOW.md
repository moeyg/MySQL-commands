# CURDATE & CURTIME & NOW

- `CURDATE` : 현재 날짜를 YYYY-MM-DD 형식의 문자열로 반환<br>
- `CURTIME` : 현재 시간을 HH:MM:SS 형식의 문자열로 반환<br>
- `NOW` : 현재 날짜와 시간을 YYYY-MM-DD HH:MM:SS 형식의 문자열로 반환<br>

  ```sql
  -- INSERT datas

  INSERT INTO PRODUCT_INFO (NAME, MFG_DATE, MFG_TIME, EXP)
  VALUES ("Monster", CURDATE(), CURTIME(), NOW());
  ```
  ```sql
  -- Result

  SELECT * FROM PRODUCT_INFO;
  +-------------+------------+----------+---------------------+
  | NAME        | MFG_DATE   | MFG_TIME | EXP                 |
  +-------------+------------+----------+---------------------+
  | CocaCola    | 2023-03-03 | 03:03:03 | 2025-05-05 05:05:05 |
  | Sprite      | 2023-04-24 | 22:22:22 | 2025-01-31 23:00:10 |
  | PocariSweat | 2023-01-01 | 00:00:05 | 2024-12-28 01:20:28 |
  | Pepsi       | 2023-06-06 | 06:06:06 | 2026-11-28 09:09:09 |
  | Monster     | 2023-04-21 | 15:11:04 | 2023-04-21 15:11:04 |
  +-------------+------------+----------+---------------------+
  ```
