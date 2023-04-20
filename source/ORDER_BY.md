# ORDER BY

- `ORDER BY` : 오름차순 결과 정렬 연산자 (Asencding default)

  ```sql
  SELECT TITLE, STOCK_QUANTITY
  FROM BOOKS
  ORDER BY STOCK_QUANTITY;
  +-----------------------------------------------------+----------------+
  | TITLE                                               | STOCK_QUANTITY |
  +-----------------------------------------------------+----------------+
  | American Gods                                       |             12 |
  | Where I'm Calling From: Selected Stories            |             12 |
  | What We Talk About When We Talk About Love: Stories |             23 |
  | The Circle                                          |             26 |
  | 10% Happier                                         |             29 |
  | The Namesake                                        |             32 |
  | Norse Mythology                                     |             43 |
  | White Noise                                         |             49 |
  | Just Kids                                           |             55 |
  | The Amazing Adventures of Kavalier & Clay           |             68 |
  | Consider the Lobster                                |             92 |
  | Cannery Row                                         |             95 |
  | Interpreter of Maladies                             |             97 |
  | Coraline                                            |            100 |
  | A Heartbreaking Work of Staggering Genius           |            104 |
  | A Hologram for the King: A Novel                    |            154 |
  | Oblivion: Stories                                   |            172 |
  | FAKE_BOOK                                           |            287 |
  | Lincoln In The Bardo                                |           1000 |
  +-----------------------------------------------------+----------------+
  ```

  ```sql
  SELECT TITLE, RELEASED_YEAR, PAGES
  FROM BOOKS
  ORDER BY RELEASED_YEAR;
  +-----------------------------------------------------+---------------+-------+
  | TITLE                                               | RELEASED_YEAR | PAGES |
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
  ```

    <br>

- `DESC` : 결과 정렬을 내림차순으로

  ```sql
  SELECT TITLE
  FROM BOOKS
  ORDER BY TITLE DESC;
  +-----------------------------------------------------+
  | TITLE                                               |
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
  ```

  ```sql
  SELECT TITLE, RELEASED_YEAR, PAGES
  FROM BOOKS
  ORDER BY RELEASERD_YEAR;
  +-----------------------------------------------------+---------------+-------+
  | TITLE                                               | RELEASED_YEAR | PAGES |
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
  ```

  <br>

- `ORDER BY first, second` : `first` 조건으로 정렬한 뒤, `second` 조건에 따라 정렬
  ```sql
  SELECT
  DISTINCT AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME
  FROM BOOKS
  ORDER BY AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME;
  +-------------------+------------------+
  | AUTHOR_FIRST_NAME | AUTHOR_LAST_NAME |
  +-------------------+------------------+
  | Dan               | Harris           |
  | Dave              | Eggers           |
  | David             | Foster Wallace   |
  | Don               | DeLillo          |
  | Freida            | Harris           |
  | George            | Saunders         |
  | Jhumpa            | Lahiri           |
  | John              | Steinbeck        |
  | Michael           | Chabon           |
  | Neil              | Gaiman           |
  | Patti             | Smith            |
  | Raymond           | Carver           |
  +-------------------+------------------+
  ```
