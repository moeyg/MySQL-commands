# REPLACE

- `REPLACE` : 첫 번째 인자의 값에서 두 번째 인자를 세 번째 인자의 값으로 치환하기

  ```sql
  SELECT
  REPLACE("Hello, World!", "Hello", "%^&$#");
  +--------------------------------------------+
  | REPLACE("Hello, World!", "Hello", "%^&$#") |
  +--------------------------------------------+
  | %^&$#, World!                              |
  +--------------------------------------------+

  -- Case sensitive

  SELECT REPLACE("Hello, World!", "o", "0");
  +------------------------------------+
  | REPLACE("Hello, World!", "o", "0") |
  +------------------------------------+
  | Hell0, W0rld!                      |
  +------------------------------------+
  ```

  ```sql
  SELECT
  REPLACE(TITLE, "e", "%") AS "REPLACE TITLE"
  FROM BOOKS;
  +-----------------------------------------------------+
  | REPLACE TITLE                                       |
  +-----------------------------------------------------+
  | Th% Nam%sak%                                        |
  | Nors% Mythology                                     |
  | Am%rican Gods                                       |
  | Int%rpr%t%r of Maladi%s                             |
  | A Hologram for th% King: A Nov%l                    |
  | Th% Circl%                                          |
  | Th% Amazing Adv%ntur%s of Kavali%r & Clay           |
  | Just Kids                                           |
  | A H%artbr%aking Work of Stagg%ring G%nius           |
  | Coralin%                                            |
  | What W% Talk About Wh%n W% Talk About Lov%: Stori%s |
  | Wh%r% I'm Calling From: S%l%ct%d Stori%s            |
  | Whit% Nois%                                         |
  | Cann%ry Row                                         |
  | Oblivion: Stori%s                                   |
  | Consid%r th% Lobst%r                                |
  | 10% Happi%r                                         |
  | FAKE_BOOK                                           |
  | Lincoln In Th% Bardo                                |
  +-----------------------------------------------------+
  ```

<br>

- `SUBSTRING` + `REPLACE` Example
  ```sql
  SELECT
  SUBSTRING(REPLACE(TITLE, "e", "%"), 1, 10) AS "SUBSTRING + REPLACE"
  FROM BOOKS;
  +---------------------+
  | SUBSTRING + REPLACE |
  +---------------------+
  | Th% Nam%sa          |
  | Nors% Myth          |
  | Am%rican G          |
  | Int%rpr%t%          |
  | A Hologram          |
  | Th% Circl%          |
  | Th% Amazin          |
  | Just Kids           |
  | A H%artbr%          |
  | Coralin%            |
  | What W% Ta          |
  | Wh%r% I'm           |
  | Whit% Nois          |
  | Cann%ry Ro          |
  | Oblivion:           |
  | Consid%r t          |
  | 10% Happi%          |
  | FAKE_BOOK           |
  | Lincoln In          |
  +---------------------+
  ```
