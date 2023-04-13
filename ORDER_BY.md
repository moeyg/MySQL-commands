# ORDER BY

- `ORDER BY` : 오름차순 결과 정렬 연산자 (Asencding default)

  ```sql
  mysql> SELECT title
      -> FROM books
      -> ORDER BY title;
  +-----------------------------------------------------+
  | title                                               |
  +-----------------------------------------------------+
  | 10% Happier                                         |
  | A Heartbreaking Work of Staggering Genius           |
  | A Hologram for the King: A Novel                    |
  | American Gods                                       |
  | Cannery Row                                         |
  | Consider the Lobster                                |
  | Coraline                                            |
  | fake_book                                           |
  | Interpreter of Maladies                             |
  | Just Kids                                           |
  | Lincoln In The Bardo                                |
  | Norse Mythology                                     |
  | Oblivion: Stories                                   |
  | The Amazing Adventures of Kavalier & Clay           |
  | The Circle                                          |
  | The Namesake                                        |
  | What We Talk About When We Talk About Love: Stories |
  | Where I'm Calling From: Selected Stories            |
  | White Noise                                         |
  +-----------------------------------------------------+
  19 rows in set (0.00 sec)
  ```

  ```sql
  mysql> SELECT title, released_year, pages
      -> FROM books
      -> ORDER BY released_year;
  +-----------------------------------------------------+---------------+-------+
  | title                                               | released_year | pages |
  +-----------------------------------------------------+---------------+-------+
  | Cannery Row                                         |          1945 |   181 |
  | What We Talk About When We Talk About Love: Stories |          1981 |   176 |
  | White Noise                                         |          1985 |   320 |
  | Where I'm Calling From: Selected Stories            |          1989 |   526 |
  | Interpreter of Maladies                             |          1996 |   198 |
  | The Amazing Adventures of Kavalier & Clay           |          2000 |   634 |
  | American Gods                                       |          2001 |   465 |
  | A Heartbreaking Work of Staggering Genius           |          2001 |   437 |
  | fake_book                                           |          2001 |   428 |
  | The Namesake                                        |          2003 |   291 |
  | Coraline                                            |          2003 |   208 |
  | Oblivion: Stories                                   |          2004 |   329 |
  | Consider the Lobster                                |          2005 |   343 |
  | Just Kids                                           |          2010 |   304 |
  | A Hologram for the King: A Novel                    |          2012 |   352 |
  | The Circle                                          |          2013 |   504 |
  | 10% Happier                                         |          2014 |   256 |
  | Norse Mythology                                     |          2016 |   304 |
  | Lincoln In The Bardo                                |          2017 |   367 |
  +-----------------------------------------------------+---------------+-------+
  19 rows in set (0.00 sec)
  ```

    <br>

- `DESC` : 결과 정렬을 내림차순으로

  ```sql
  mysql> SELECT title
      -> FROM books
      -> ORDER BY title
      -> DESC;
  +-----------------------------------------------------+
  | title                                               |
  +-----------------------------------------------------+
  | White Noise                                         |
  | Where I'm Calling From: Selected Stories            |
  | What We Talk About When We Talk About Love: Stories |
  | The Namesake                                        |
  | The Circle                                          |
  | The Amazing Adventures of Kavalier & Clay           |
  | Oblivion: Stories                                   |
  | Norse Mythology                                     |
  | Lincoln In The Bardo                                |
  | Just Kids                                           |
  | Interpreter of Maladies                             |
  | fake_book                                           |
  | Coraline                                            |
  | Consider the Lobster                                |
  | Cannery Row                                         |
  | American Gods                                       |
  | A Hologram for the King: A Novel                    |
  | A Heartbreaking Work of Staggering Genius           |
  | 10% Happier                                         |
  +-----------------------------------------------------+
  19 rows in set (0.00 sec)
  ```

  ```sql
  mysql> SELECT title, released_year, pages
      -> FROM books
      -> ORDER BY released_year;
  +-----------------------------------------------------+---------------+-------+
  | title                                               | released_year | pages |
  +-----------------------------------------------------+---------------+-------+
  | Cannery Row                                         |          1945 |   181 |
  | What We Talk About When We Talk About Love: Stories |          1981 |   176 |
  | White Noise                                         |          1985 |   320 |
  | Where I'm Calling From: Selected Stories            |          1989 |   526 |
  | Interpreter of Maladies                             |          1996 |   198 |
  | The Amazing Adventures of Kavalier & Clay           |          2000 |   634 |
  | American Gods                                       |          2001 |   465 |
  | A Heartbreaking Work of Staggering Genius           |          2001 |   437 |
  | fake_book                                           |          2001 |   428 |
  | The Namesake                                        |          2003 |   291 |
  | Coraline                                            |          2003 |   208 |
  | Oblivion: Stories                                   |          2004 |   329 |
  | Consider the Lobster                                |          2005 |   343 |
  | Just Kids                                           |          2010 |   304 |
  | A Hologram for the King: A Novel                    |          2012 |   352 |
  | The Circle                                          |          2013 |   504 |
  | 10% Happier                                         |          2014 |   256 |
  | Norse Mythology                                     |          2016 |   304 |
  | Lincoln In The Bardo                                |          2017 |   367 |
  +-----------------------------------------------------+---------------+-------+
  19 rows in set (0.01 sec)
  ```

  <br>

- `ORDER BY first, second` : `first` 조건으로 정렬한 뒤, `second` 조건에 따라 정렬
  ```sql
  mysql> SELECT author_fname, author_lname
      -> FROM books
      -> ORDER BY author_lname, author_fname;
  +--------------+----------------+
  | author_fname | author_lname   |
  +--------------+----------------+
  | Raymond      | Carver         |
  | Raymond      | Carver         |
  | Michael      | Chabon         |
  | Don          | DeLillo        |
  | Dave         | Eggers         |
  | Dave         | Eggers         |
  | Dave         | Eggers         |
  | David        | Foster Wallace |
  | David        | Foster Wallace |
  | Neil         | Gaiman         |
  | Neil         | Gaiman         |
  | Neil         | Gaiman         |
  | Dan          | Harris         |
  | Freida       | Harris         |
  | Jhumpa       | Lahiri         |
  | Jhumpa       | Lahiri         |
  | George       | Saunders       |
  | Patti        | Smith          |
  | John         | Steinbeck      |
  +--------------+----------------+
  19 rows in set (0.00 sec)
  ```
