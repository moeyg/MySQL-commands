# TIMESTAMP

- 날짜와 시간 정보를 저장하는 데이터 타입 중 하나로, 특정 시점의 날짜와 시간을 나타낸다.<br>
- `YYYY-MM-DD HH:MM:SS` 형식으로 날짜와 시간 저장<br>
- MySQL 서버의 시간대를 기준으로 저장<br>
- 4바이트 혹은 8바이트로 저장<br>
- '1970-01-01 00:00:00'부터 '2038-01-19 03:14:07'까지의 범위를 지원<br>
- 자동으로 업데이트 되는 기능을 가지고 있어, 데이터가 삽입되거나 수정될 때 자동으로 현재 날짜와 시간으로 갱신될 수 있다.<br>

  ```sql
  -- CREATE TABLE

  CREATE TABLE COMMENTS
  (
        CONTENTS VARCHAR(255),
        CREATED_AT TIMESTAMP DEFAULT NOW()
   );
  ```
  ```sql
  -- INSERT datas

  INSERT INTO COMMENTS (CONTENTS) VALUES ("Hello, World!");

  INSERT INTO COMMENTS (CONTENTS) VALUES ("Hello, DataBase!");

  INSERT INTO COMMENTS (CONTENTS) VALUES ("Hello, MySQL!");
  ```
  ```sql
  -- Result

  SELECT *
  FROM COMMENTS
  ORDER BY CREATED_AT DESC;
  +------------------+---------------------+
  | CONTENTS         | CREATED_AT          |
  +------------------+---------------------+
  | Hello, MySQL!    | 2023-04-22 23:04:32 |
  | Hello, DataBase! | 2023-04-22 23:03:56 |
  | Hello, World!    | 2023-04-22 23:03:31 |
  +------------------+---------------------+
  ```

<br>

- `ON UPDATE CURRENT_TIMESTAMP` : 해당 COLUMN이 업데이트될 때 자동으로 현재 날짜와 시간(`CURRENT_TIMESTAMP`)로 갱신되도록 설정한다.

  ```sql
  -- CREATE TABLE

  CREATE TABLE COMMENTS
  (
      CONTENTS VARCHAR(255),
      UPDATED_AT TIMESTAMP DEFAULT NOW() ON UPDATE CURRENT_TIMESTAMP
  );
  ```
  ```sql
  -- INSERT datas

  INSERT INTO COMMENTS (CONTENTS) VALUES ("Hello, World!");

  INSERT INTO COMMENTS (CONTENTS) VALUES ("Hello, DataBase!");

  INSERT INTO COMMENTS (CONTENTS) VALUES ("Hello, MySQL!");
  ```
  ```sql
  -- Result

  SELECT * FROM COMMENTS;
  +------------------+---------------------+
  | CONTENTS         | UPDATED_AT          |
  +------------------+---------------------+  
  | Hello, World!    | 2023-04-22 23:08:02 |
  | Hello, DataBase! | 2023-04-22 23:08:27 |
  | Hello, MySQL!    | 2023-04-22 23:08:34 |
  +------------------+---------------------+
  ```
  ```sql
  -- Update content

  UPDATE COMMENTS
  SET CONTENTS="Hello, World :)"
  WHERE CONTENTS="Hello, World!";

  UPDATE COMMENTS
  SET CONTENTS="Hello, DataBase :)"
  WHERE CONTENTS="Hello, DataBase!";

  UPDATE COMMENTS
  SET CONTENTS="Hello, MySQL :)"
  WHERE CONTENTS="Hello, MySQL!";
  ```
  ```sql
  -- Result

  SELECT *
  FROM COMMENTS
  ORDER BY UPDATED_AT DESC;
  +--------------------+---------------------+
  | CONTENTS           | UPDATED_AT          |
  +--------------------+---------------------+
  | Hello, MySQL :)    | 2023-04-22 23:11:35 |  -- 업데이트 된 시간 반영
  | Hello, DataBase :) | 2023-04-22 23:10:56 |
  | Hello, World :)    | 2023-04-22 23:10:07 |
  +--------------------+---------------------+
  ```
