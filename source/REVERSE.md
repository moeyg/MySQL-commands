# REVERSE

- `REVERSE` : 문자열 반전하기
  ```sql
  SELECT REVERSE("Hello, World!");
  +--------------------------+
  | REVERSE("Hello, World!") |
  +--------------------------+
  | !dlroW ,olleH            |
  +--------------------------+
  ```
  ```sql
  SELECT
  REVERSE(TITLE)
  FROM BOOKS;
  +-----------------------------------------------------+
  | REVERSE(TITLE)                                      |
  +-----------------------------------------------------+
  | ekasemaN ehT                                        |
  | ygolohtyM esroN                                     |
  | sdoG naciremA                                       |
  | seidalaM fo reterpretnI                             |
  | levoN A :gniK eht rof margoloH A                    |
  | elcriC ehT                                          |
  | yalC & reilavaK fo serutnevdA gnizamA ehT           |
  | sdiK tsuJ                                           |
  | suineG gnireggatS fo kroW gnikaerbtraeH A           |
  | enilaroC                                            |
  | seirotS :evoL tuobA klaT eW nehW tuobA klaT eW tahW |
  | seirotS detceleS :morF gnillaC m'I erehW            |
  | esioN etihW                                         |
  | woR yrennaC                                         |
  | seirotS :noivilbO                                   |
  | retsboL eht redisnoC                                |
  | reippaH %01                                         |
  | KOOB_EKAF                                           |
  | odraB ehT nI nlocniL                                |
  +-----------------------------------------------------+
  ```

<br>

- `CONCAT` + `REVERSE` Example
  ```sql
  SELECT
  CONCAT(AUTHOR_FIRST_NAME, REVERSE(AUTHOR_LAST_NAME)) AS "WEIRD NAME"
  FROM BOOKS;
  +---------------------+
  | WEIRD NAME          |
  +---------------------+
  | JhumpairihaL        |
  | NeilnamiaG          |
  | NeilnamiaG          |
  | JhumpairihaL        |
  | DavesreggE          |
  | DavesreggE          |
  | MichaelnobahC       |
  | PattihtimS          |
  | DavesreggE          |
  | NeilnamiaG          |
  | RaymondrevraC       |
  | RaymondrevraC       |
  | DonolliLeD          |
  | JohnkcebnietS       |
  | DavidecallaW retsoF |
  | DavidecallaW retsoF |
  | DansirraH           |
  | FreidasirraH        |
  | GeorgesrednuaS      |
  +---------------------+
  ```
