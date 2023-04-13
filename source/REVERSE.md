# REVERSE

- `REVERSE` : 문자열 반전하기
  ```bash
  mysql> SELECT REVERSE('Hello, World!');
  +--------------------------+
  | REVERSE('Hello, World!') |
  +--------------------------+
  | !dlroW ,olleH            |
  +--------------------------+
  1 row in set (0.00 sec)
  ```
  ```bash
  mysql> SELECT REVERSE(author_fname) FROM books;
  +-----------------------+
  | REVERSE(author_fname) |
  +-----------------------+
  | apmuhJ                |
  | lieN                  |
  | lieN                  |
  | apmuhJ                |
  | evaD                  |
  | evaD                  |
  | leahciM               |
  | ittaP                 |
  | evaD                  |
  | lieN                  |
  | dnomyaR               |
  | dnomyaR               |
  | noD                   |
  | nhoJ                  |
  | divaD                 |
  | divaD                 |
  +-----------------------+
  16 rows in set (0.00 sec)
  ```

<br>

- `CONCAT` + `REVERSE` Example
  ```bash
  mysql> SELECT
      -> CONCAT
      -> (author_fname, REVERSE(author_fname))
      -> AS 'weird name'
      -> FROM books;
  +----------------+
  | weird name     |
  +----------------+
  | JhumpaapmuhJ   |
  | NeillieN       |
  | NeillieN       |
  | JhumpaapmuhJ   |
  | DaveevaD       |
  | DaveevaD       |
  | MichaelleahciM |
  | PattiittaP     |
  | DaveevaD       |
  | NeillieN       |
  | RaymonddnomyaR |
  | RaymonddnomyaR |
  | DonnoD         |
  | JohnnhoJ       |
  | DaviddivaD     |
  | DaviddivaD     |
  +----------------+
  16 rows in set (0.00 sec)
  ```
