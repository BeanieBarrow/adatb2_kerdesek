# adatb2_kerdesek

ELTE IK BSc, Adatbázisok II. szóbeli vizsga kérdései kidolgozva.

## Hogyan kapok ebből PDF-et, HTML-t vagy docx-et?

Használd a [pandoc](https://pandoc.org/)-ot, telepítsd, ha nincs meg, nyiss a
`kerdesek.md` könyvtárában egy parancssort, és add ki ezen parancsok egyikét:

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
