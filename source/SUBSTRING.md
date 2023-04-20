# SUBSTRING

- `SUBSTRING` : 문자열을 인덱스에 따라 자르기

  ```sql
  -- Two index

  SELECT SUBSTRING("Hello, World!", 1, 6);
  +----------------------------------+
  | SUBSTRING("Hello, World!", 1, 6) |
  +----------------------------------+
  | Hello,                           |
  +----------------------------------+
  ```
  ```sql
  -- One index

  SELECT SUBSTRING("Hello, World!", 7);
  +-------------------------------+
  | SUBSTRING("Hello, World!", 7) |
  +-------------------------------+
  |  World!                       |
  +-------------------------------+
  ```
  ```sql
  -- Negative index

  SELECT SUBSTRING("Hello, World!", -5);
  +--------------------------------+
  | SUBSTRING("Hello, World!", -5) |
  +--------------------------------+
  | orld!                          |
  +--------------------------------+
  ```
  ```sql
  SELECT
  SUBSTRING(TITLE, 1, 10)
  FROM BOOKS;
  +-------------------------+
  | SUBSTRING(TITLE, 1, 10) |
  +-------------------------+
  | The Namesa              |
  | Norse Myth              |
  | American G              |
  | Interprete              |
  | A Hologram              |
  | The Circle              |
  | The Amazin              |
  | Just Kids               |
  | A Heartbre              |
  | Coraline                |
  | What We Ta              |
  | Where I'm               |
  | White Nois              |
  | Cannery Ro              |
  | Oblivion:               |
  | Consider t              |
  | 10% Happie              |
  | FAKE_BOOK               |
  | Lincoln In              |
  +-------------------------+
  ```
  ```sql
  -- Use AS

  SELECT
  SUBSTRING(TITLE, 1, 10) AS "TITLE: LENGTH 10"
  FROM BOOKS;
  +------------------+
  | TITLE: LENGTH 10 |
  +------------------+
  | The Namesa       |
  | Norse Myth       |
  | American G       |
  | Interprete       |
  | A Hologram       |
  | The Circle       |
  | The Amazin       |
  | Just Kids        |
  | A Heartbre       |
  | Coraline         |
  | What We Ta       |
  | Where I'm        |
  | White Nois       |
  | Cannery Ro       |
  | Oblivion:        |
  | Consider t       |
  | 10% Happie       |
  | FAKE_BOOK        |
  | Lincoln In       |
  +------------------+
  ```

<br>

- `CONCAT` + `SUBSTRING` Example
  ```sql
  SELECT
  CONCAT(SUBSTRING(TITLE, 1, 10), "...")
  AS "ELLIPSIS"
  FROM BOOKS;
  +---------------+
  | ELLIPSIS      |
  +---------------+
  | The Namesa... |
  | Norse Myth... |
  | American G... |
  | Interprete... |
  | A Hologram... |
  | The Circle... |
  | The Amazin... |
  | Just Kids...  |
  | A Heartbre... |
  | Coraline...   |
  | What We Ta... |
  | Where I'm ... |
  | White Nois... |
  | Cannery Ro... |
  | Oblivion: ... |
  | Consider t... |
  | 10% Happie... |
  | FAKE_BOOK...  |
  | Lincoln In... |
  +---------------+
  ```
