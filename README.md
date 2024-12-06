# Adatbázisok II. kérdések

ELTE IK BSc, Adatbázisok II. szóbeli vizsga kérdései kidolgozva.

Természetesen fenntartjuk a lehetőséget, hogy a válaszaink nem
100%-ban jók. Ennek tudatában használjátok a repot.

## Hogyan kapok ebből PDF-et, HTML-t vagy docx-et?

Használd a [pandoc](https://pandoc.org/) programot. Telepítsd, ha nincs meg:

### Pandoc telepítés (Windows):

- Nyiss parancssort rendszergazdaként, majd a futtasd az alábbi parancsokat:
- [Chocolatey](https://chocolatey.org/) csomagkezelő telepítése Powershellel:
- Ennél részletesebb, naprakészebb útmutató: https://chocolatey.org/install

```bash
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "[System.Net.ServicePointManager]::SecurityProtocol = 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

- `pandoc` telepítése Chocolatey-vel:

```
choco install pandoc
```

- Ha megvan, nyiss a `kerdesek.md` könyvtárában egy parancssort, és add ki ezen
  parancsok egyikét:

### HTML esetén (ajánlott):

```bash
pandoc kerdesek.md -o kerdesek.html
```

### PDF esetén:

```bash
pandoc --pdf-engine=xelatex -V "mainfont:DejaVu Sans" -V "monofont:DejaVu Sans Mono" kerdesek.md -o kerdesek.pdf -V geometry:margin=0.5in -f markdown-implicit_figures
```

### docx esetén:

```bash
pandoc kerdesek.md -o kerdesek.docx
```

## Kikérdezés

### Shellből egy véletlen kérdés

Ha [Fish shellt](https://fishshell.com/) használsz (a `random` függvényhez
kell, szabadon átírható bash-re is, csak lusta vagyok), akkor ezzel a kétsoros
paranccsal kaphatsz egy véletlenszerű kérdést:

```bash
set random_line (random 1 248)
echo $random_line | grep "## $random_line." -m 1 kerdesek.md
```

### Flashkártyák

Egy modern flashkártyás megoldást [Attila121](https://github.com/Attila121) írt.
A repo megtalálható itt: [https://github.com/Attila121/Adatbazisok2_flash_cards](https://github.com/Attila121/Adatbazisok2_flash_cards).

Ezen az oldalon kipróbálható: [https://attila121.github.io/Adatbazisok2_flash_cards/](https://attila121.github.io/Adatbazisok2_flash_cards/)

## „Megváltoztak azóta a vizsgakérdések.”

A repo a 2023/2024/II. félévben készült. Benne van a pakliban, hogy megváltozott a kérdéssor.

Ha ilyen történt, akkor az itt lévő `Ellenorzokerdesek.docx` fájlt cseréljétek ki a commitotokban az éppen aktuális kérdéssorra, légyszi.

Jó kérdés, mi van akkor, ha lettek új kérdések a vizsgán, de a régiekből is eltűnt pár. Töröljük a régieket? Írjuk felül az eddigieket? A válasz az, hogy nem tudom, majd az adott pull request alatt megbeszéljük. :D

Elvileg bárki nyithat pull requestet itt, ezek belátható időn belül el lesznek fogadva.

Köszi a segítségetek! Sok sikert a vizsgához.
