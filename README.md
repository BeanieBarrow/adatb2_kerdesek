# adatb2_kerdesek

ELTE IK BSc, Adatbázisok II. szóbeli vizsga kérdései kidolgozva.

## Hogyan kapok ebből PDF-et vagy docx-et?

Használd a [pandoc](https://pandoc.org/)-ot, telepítsd, ha nincs meg, nyiss a
`kerdesek.md` könyvtárában egy parancssort, és add ki ezen parancsok egyikét:

```bash
pandoc --pdf-engine=xelatex -V "mainfont:DejaVu Sans" -V "monofont:DejaVu Sans Mono" kerdesek.md -o kerdesek.pdf
```

Vagy:

```bash
pandoc kerdesek.md -o kerdesek.docx
```
