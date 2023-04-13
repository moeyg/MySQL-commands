# UPPER & LOWER

- `UPPER` : 문자열을 대문자로 치환하기

      ```bash
      mysql> SELECT UPPER("hello, world!!");
      +------------------------+
      | UPPER("hello, world!") |
      +------------------------+
      | HELLO, WORLD!!         |
      +------------------------+
      1 row in set (0.00 sec)
      ```

      ```bash
      mysql> SELECT
          -> CONCAT
          -> ("MY FAVORITE BOOK IS ", UPPER(title))
          -> AS "FAVORITE BOOKS"
          -> FROM books;
      +-------------------------------------------------------------------------+
      | FAVORITE BOOKS                                                          |
      +-------------------------------------------------------------------------+
      | MY FAVORITE BOOK IS THE NAMESAKE                                        |
      | MY FAVORITE BOOK IS NORSE MYTHOLOGY                                     |
      | MY FAVORITE BOOK IS AMERICAN GODS                                       |
      | MY FAVORITE BOOK IS INTERPRETER OF MALADIES                             |
      | MY FAVORITE BOOK IS A HOLOGRAM FOR THE KING: A NOVEL                    |
      | MY FAVORITE BOOK IS THE CIRCLE                                          |
      | MY FAVORITE BOOK IS THE AMAZING ADVENTURES OF KAVALIER & CLAY           |
      | MY FAVORITE BOOK IS JUST KIDS                                           |
      | MY FAVORITE BOOK IS A HEARTBREAKING WORK OF STAGGERING GENIUS           |
      | MY FAVORITE BOOK IS CORALINE                                            |
      | MY FAVORITE BOOK IS WHAT WE TALK ABOUT WHEN WE TALK ABOUT LOVE: STORIES |
      | MY FAVORITE BOOK IS WHERE I'M CALLING FROM: SELECTED STORIES            |
      | MY FAVORITE BOOK IS WHITE NOISE                                         |
      | MY FAVORITE BOOK IS CANNERY ROW                                         |
      | MY FAVORITE BOOK IS OBLIVION: STORIES                                   |
      | MY FAVORITE BOOK IS CONSIDER THE LOBSTER                                |
      +-------------------------------------------------------------------------+
      16 rows in set (0.00 sec)
      ```

  <br>

- `LOWER` : 문자열을 소문자로 치환하기
  ```bash
  mysql> SELECT LOWER("HELLO, WORLD!");
  +------------------------+
  | LOWER("HELLO, WORLD!") |
  +------------------------+
  | hello, world!          |
  +------------------------+
  1 row in set (0.00 sec)
  ```
  ```bash
  mysql> SELECT
      -> CONCAT
      -> ("my favorite book is ", LOWER(title))
      -> AS "favorite boosk"
      -> FROM books;
  +-------------------------------------------------------------------------+
  | favorite boosk                                                          |
  +-------------------------------------------------------------------------+
  | my favorite book is the namesake                                        |
  | my favorite book is norse mythology                                     |
  | my favorite book is american gods                                       |
  | my favorite book is interpreter of maladies                             |
  | my favorite book is a hologram for the king: a novel                    |
  | my favorite book is the circle                                          |
  | my favorite book is the amazing adventures of kavalier & clay           |
  | my favorite book is just kids                                           |
  | my favorite book is a heartbreaking work of staggering genius           |
  | my favorite book is coraline                                            |
  | my favorite book is what we talk about when we talk about love: stories |
  | my favorite book is where i'm calling from: selected stories            |
  | my favorite book is white noise                                         |
  | my favorite book is cannery row                                         |
  | my favorite book is oblivion: stories                                   |
  | my favorite book is consider the lobster                                |
  +-------------------------------------------------------------------------+
  16 rows in set (0.00 sec)
  ```
