# CONCAT

- `SOURCE` : 파일 불러오기
  ```sql
  SOURCE /Users/moeyg/Database/BOOK_STORE.sql
  ```

<br>

- `CONCAT` : 문자열 연결 함수

  ```sql
  SELECT AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME
  FROM BOOKS;
  +-------------------+------------------+
  | AUTHOR_FIRST_NAME | AUTHOR_LAST_NAME |
  +-------------------+------------------+
  | Jhumpa            | Lahiri           |
  | Neil              | Gaiman           |
  | Neil              | Gaiman           |
  | Jhumpa            | Lahiri           |
  | Dave              | Eggers           |
  | Dave              | Eggers           |
  | Michael           | Chabon           |
  | Patti             | Smith            |
  | Dave              | Eggers           |
  | Neil              | Gaiman           |
  | Raymond           | Carver           |
  | Raymond           | Carver           |
  | Don               | DeLillo          |
  | John              | Steinbeck        |
  | David             | Foster Wallace   |
  | David             | Foster Wallace   |
  | Dan               | Harris           |
  | Freida            | Harris           |
  | George            | Saunders         |
  +-------------------+------------------+
  ```

  ```sql
  -- Use CONCAT function

  SELECT
  CONCAT(AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME)
  FROM BOOKS;
  +---------------------------------------------+
  | CONCAT(AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME) |
  +---------------------------------------------+
  | JhumpaLahiri                                |
  | NeilGaiman                                  |
  | NeilGaiman                                  |
  | JhumpaLahiri                                | 
  | DaveEggers                                  |
  | DaveEggers                                  |
  | MichaelChabon                               |
  | PattiSmith                                  |
  | DaveEggers                                  |
  | NeilGaiman                                  |
  | RaymondCarver                               |
  | RaymondCarver                               |
  | DonDeLillo                                  |
  | JohnSteinbeck                               |
  | DavidFoster Wallace                         |
  | DavidFoster Wallace                         |
  | DanHarris                                   |
  | FreidaHarris                                |
  | GeorgeSaunders                              |
  +---------------------------------------------+
  ```

<br>

- `CONCAT AS` : 문자열을 결합한 자료에 별칭 붙이기

  ```sql
  -- Use AS

  SELECT
  CONCAT(AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME) AS "AUTHOR_FULL_NAME"
  FROM BOOKS;
  +---------------------+
  | AUTHOR_FULL_NAME    |
  +---------------------+
  | JhumpaLahiri        |
  | NeilGaiman          |
  | NeilGaiman          |
  | JhumpaLahiri        |
  | DaveEggers          |
  | DaveEggers          |
  | MichaelChabon       |
  | PattiSmith          |
  | DaveEggers          |
  | NeilGaiman          |
  | RaymondCarver       |
  | RaymondCarver       |
  | DonDeLillo          |
  | JohnSteinbeck       |
  | DavidFoster Wallace |
  | DavidFoster Wallace |
  | DanHarris           |
  | FreidaHarris        |
  | GeorgeSaunders      |
  +---------------------+
  ```

  <br>

- `CONCAT` Example
  ```sql
  SELECT AUTHOR_FIRST_NAME AS "FIRST NAME",
         AUTHOR_LAST_NAME AS "LAST NAME",
         CONCAT(AUTHOR_FIRST_NAME, ", ", AUTHOR_LAST_NAME) AS "FULL NAME"
  FROM BOOKS;
  +------------+----------------+-----------------------+
  | FIRST NAME | LAST NAME      | FULL NAME             |
  +------------+----------------+-----------------------+
  | Jhumpa     | Lahiri         | Jhumpa, Lahiri        |
  | Neil       | Gaiman         | Neil, Gaiman          |
  | Neil       | Gaiman         | Neil, Gaiman          |
  | Jhumpa     | Lahiri         | Jhumpa, Lahiri        |
  | Dave       | Eggers         | Dave, Eggers          |
  | Dave       | Eggers         | Dave, Eggers          |
  | Michael    | Chabon         | Michael, Chabon       |
  | Patti      | Smith          | Patti, Smith          |
  | Dave       | Eggers         | Dave, Eggers          |
  | Neil       | Gaiman         | Neil, Gaiman          |
  | Raymond    | Carver         | Raymond, Carver       |
  | Raymond    | Carver         | Raymond, Carver       |
  | Don        | DeLillo        | Don, DeLillo          |
  | John       | Steinbeck      | John, Steinbeck       |
  | David      | Foster Wallace | David, Foster Wallace |
  | David      | Foster Wallace | David, Foster Wallace |
  +------------+----------------+-----------------------+
  ```

<br>

- `CONCAT_WS` : 처음 인자를 구분자로 하여, 나머지 인자들을 결합
  ```sql
  SELECT
  CONCAT_WS(": ", TITLE, CONCAT(AUTHOR_FIRST_NAME, AUTHOR_LAST_NAME))
  AS "TITLE: AUTHOR"
  FROM BOOKS;
  +--------------------------------------------------------------------+
  | TITLE: AUTHOR                                                      |
  +--------------------------------------------------------------------+
  | The Namesake: JhumpaLahiri                                         |
  | Norse Mythology: NeilGaiman                                        |
  | American Gods: NeilGaiman                                          |
  | Interpreter of Maladies: JhumpaLahiri                              |
  | A Hologram for the King: A Novel: DaveEggers                       |
  | The Circle: DaveEggers                                             |
  | The Amazing Adventures of Kavalier & Clay: MichaelChabon           |
  | Just Kids: PattiSmith                                              |
  | A Heartbreaking Work of Staggering Genius: DaveEggers              |
  | Coraline: NeilGaiman                                               |
  | What We Talk About When We Talk About Love: Stories: RaymondCarver |
  | Where I'm Calling From: Selected Stories: RaymondCarver            |
  | White Noise: DonDeLillo                                            |
  | Cannery Row: JohnSteinbeck                                         |
  | Oblivion: Stories: DavidFoster Wallace                             |
  | Consider the Lobster: DavidFoster Wallace                          |
  | 10% Happier: DanHarris                                             |
  | FAKE_BOOK: FreidaHarris                                            |
  | Lincoln In The Bardo: GeorgeSaunders                               |
  +--------------------------------------------------------------------+
  ```
