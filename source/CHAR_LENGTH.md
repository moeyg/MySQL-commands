# CHAR_LENGTH

- `CHAR_LENGTH` : 문자열의 길이 구하기
  ```sql
  SELECT CHAR_LENGTH("Hello, World!");
  +------------------------------+
  | CHAR_LENGTH("Hello, World!") |
  +------------------------------+
  |                           13 |
  +------------------------------+
  ```
  ```sql
  SELECT TITLE,
         CHAR_LENGTH(TITLE) AS "TITLE LENGTH"
  FROM BOOKS;
  +-----------------------------------------------------+--------------+
  | TITLE                                               | TITLE LENGTH |
  +-----------------------------------------------------+--------------+
  | The Namesake                                        |           12 |
  | Norse Mythology                                     |           15 |
  | American Gods                                       |           13 |
  | Interpreter of Maladies                             |           23 |
  | A Hologram for the King: A Novel                    |           32 |
  | The Circle                                          |           10 |
  | The Amazing Adventures of Kavalier & Clay           |           41 |
  | Just Kids                                           |            9 |
  | A Heartbreaking Work of Staggering Genius           |           41 |
  | Coraline                                            |            8 |
  | What We Talk About When We Talk About Love: Stories |           51 |
  | Where I'm Calling From: Selected Stories            |           40 |
  | White Noise                                         |           11 |
  | Cannery Row                                         |           11 |
  | Oblivion: Stories                                   |           17 |
  | Consider the Lobster                                |           20 |
  | 10% Happier                                         |           11 |
  | FAKE_BOOK                                           |            9 |
  | Lincoln In The Bardo                                |           20 |
  +-----------------------------------------------------+--------------+
  ```

<br>

- `CONCAT` + `CHAR_LENGTH` Example
  ```sql
  SELECT
  CONCAT("[", TITLE, "]",  " is ", CHAR_LENGTH(TITLE), " character length")
  AS "Character Length"
  FROM BOOKS;
  +------------------------------------------------------------------------------+
  | Character Length                                                             |
  +------------------------------------------------------------------------------+
  | [The Namesake] is 12 character length                                        |
  | [Norse Mythology] is 15 character length                                     |
  | [American Gods] is 13 character length                                       |
  | [Interpreter of Maladies] is 23 character length                             |
  | [A Hologram for the King: A Novel] is 32 character length                    |
  | [The Circle] is 10 character length                                          |
  | [The Amazing Adventures of Kavalier & Clay] is 41 character length           |
  | [Just Kids] is 9 character length                                            |
  | [A Heartbreaking Work of Staggering Genius] is 41 character length           |
  | [Coraline] is 8 character length                                             |
  | [What We Talk About When We Talk About Love: Stories] is 51 character length |
  | [Where I'm Calling From: Selected Stories] is 40 character length            |
  | [White Noise] is 11 character length                                         |
  | [Cannery Row] is 11 character length                                         |
  | [Oblivion: Stories] is 17 character length                                   |
  | [Consider the Lobster] is 20 character length                                |
  | [10% Happier] is 11 character length                                         |
  | [FAKE_BOOK] is 9 character length                                            |
  | [Lincoln In The Bardo] is 20 character length                                |
  +------------------------------------------------------------------------------+
  ```
