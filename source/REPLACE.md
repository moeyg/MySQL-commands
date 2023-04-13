# REPLACE

- `REPLACE` : 첫 번째 인자의 값에서 두 번째 인자를 세 번째 인자의 값으로 치환하기

  ```sql
  mysql> SELECT REPLACE("Hello, World!", "Hello", "%^&$#");
  +--------------------------------------------+
  | REPLACE("Hello, World!", "Hello", "%^&$#") |
  +--------------------------------------------+
  | %^&$#, World!                              |
  +--------------------------------------------+
  1 row in set (0.00 sec)

  -- Case sensitive

  mysql> SELECT REPLACE("Hello, World!", "o", "0");
  +------------------------------------+
  | REPLACE("Hello, World!", "o", "0") |
  +------------------------------------+
  | Hell0, W0rld!                      |
  +------------------------------------+
  1 row in set (0.00 sec)
  ```

  ```sql
  mysql> SELECT REPLACE(title, "e", "@")
      -> FROM books;
  +-----------------------------------------------------+
  | REPLACE(title, "e", "@")                            |
  +-----------------------------------------------------+
  | Th@ Nam@sak@                                        |
  | Nors@ Mythology                                     |
  | Am@rican Gods                                       |
  | Int@rpr@t@r of Maladi@s                             |
  | A Hologram for th@ King: A Nov@l                    |
  | Th@ Circl@                                          |
  | Th@ Amazing Adv@ntur@s of Kavali@r & Clay           |
  | Just Kids                                           |
  | A H@artbr@aking Work of Stagg@ring G@nius           |
  | Coralin@                                            |
  | What W@ Talk About Wh@n W@ Talk About Lov@: Stori@s |
  | Wh@r@ I'm Calling From: S@l@ct@d Stori@s            |
  | Whit@ Nois@                                         |
  | Cann@ry Row                                         |
  | Oblivion: Stori@s                                   |
  | Consid@r th@ Lobst@r                                |
  +-----------------------------------------------------+
  16 rows in set (0.00 sec)
  ```

<br>

- `SUBSTRING` + `REPLACE` Example
  ```sql
  mysql> SELECT
      -> SUBSTRING(
      ->     REPLACE(title, "e", "@"), 1, 10) AS "title"
      -> FROM books;
  +------------+
  | title      |
  +------------+
  | Th@ Nam@sa |
  | Nors@ Myth |
  | Am@rican G |
  | Int@rpr@t@ |
  | A Hologram |
  | Th@ Circl@ |
  | Th@ Amazin |
  | Just Kids  |
  | A H@artbr@ |
  | Coralin@   |
  | What W@ Ta |
  | Wh@r@ I'm  |
  | Whit@ Nois |
  | Cann@ry Ro |
  | Oblivion:  |
  | Consid@r t |
  +------------+
  16 rows in set (0.00 sec)
  ```
