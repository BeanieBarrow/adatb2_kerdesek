# adatb2_kerdesek

ELTE IK BSc, Adatbázisok II. szóbeli vizsga kérdései kidolgozva.

Természetesen fenntartjuk a lehetőséget, hogy a válaszaink nem
100%-ban jók. Ennek tudatában használjátok a repot.

## Hogyan kapok ebből PDF-et, HTML-t vagy docx-et?

Használd a [pandoc](https://pandoc.org/)ot, telepítsd, ha nincs meg:

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

Ha [Fish shellt](https://fishshell.com/) használsz (a `random` függvényhez
kell, szabadon átírható bash-re is, csak lusta vagyok), akkor ezzel a kétsoros
paranccsal kaphatsz egy véletlenszerű kérdést:

```bash
set random_line (random 1 248)
echo $random_line | grep "## $random_line." -m 1 kerdesek.md
```
