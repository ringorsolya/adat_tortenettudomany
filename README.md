# Adat a történettudományban

**Ring Orsolya**  
ELTE BTK Történelem Segédtudományai Tanszék, 2026

Online olvasható: [https://YOUR-USERNAME.github.io/adatTortenet/](https://YOUR-USERNAME.github.io/adatTortenet/)

---

## A könyvről

Ez a könyv a digitális módszerek alkalmazását mutatja be a történettudományban, különös tekintettel az adatgyűjtés, -kezelés és -elemzés módszertanára. Két teljes esettanulmányt tartalmaz valódi levéltári adatokon:

- **6.5. fejezet:** Egyházmegyei ösztöndíjasok prozopográfiai elemzése (1957–1975) – kollektív életrajzi módszer
- **8.5. fejezet:** A Nemzeti Színház épületvitájának szövegbányászati elemzése (1957–1988) – szöveg mint adat

---

## Fejezetek

| # | Cím | Állapot |
|---|-----|---------|
| 1 | Adat a történettudományban | ✓ Kész |
| 2 | Bibliográfiai adat és hivatkozáskezelés | Készülőben |
| 3 | Digitalizálás – Machine-readable szöveg | Készülőben |
| 4 | Forrásban lévő adat I – Történeti statisztikák | Készülőben |
| 5 | Forrásban lévő adat II – Vizualizáció | Készülőben |
| 6 | Adatbázisba rendezhető adat I – Prosopográfia | Készülőben |
| **6.5** | **Esettanulmány: Egyházmegyei ösztöndíjasok** | **✓ Kész** |
| 7 | Adatbázisba rendezhető adat II – Adattisztítás | Készülőben |
| 8 | Szöveg mint adat – Számítógépes szövegelemzés | Készülőben |
| **8.5** | **Esettanulmány: Nemzeti Színház szövegbányászat** | **✓ Kész** |
| 9 | Adatvizualizáció – Flourish és interpretáció | Készülőben |
| 10 | Adatok publikálása, dokumentáció, etika | Készülőben |

---

## Buildelés

### Előfeltételek

- R (≥ 4.0) és RStudio
- `bookdown` csomag: `install.packages("bookdown")`

### Lokális build

```r
bookdown::render_book("index.md", "bookdown::gitbook")
```

### GitHub Pages publikálás

A könyv a `docs/` mappából vagy a repo gyökeréből publikálható GitHub Pages-re. A `.github/workflows/` mappában elhelyezett action automatizálhatja a buildet minden push után.

```yaml
# .github/workflows/bookdown.yml
name: Build bookdown
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: r-lib/actions/setup-r@v2
      - run: Rscript -e 'install.packages("bookdown")'
      - run: Rscript -e 'bookdown::render_book("index.md")'
```

---

## Könyvtárszerkezet

```
.
├── index.md                    # Fedőlap és előszó
├── 01-week1.md                 # 1. fejezet forrás
├── 06-week6.md                 # 6. fejezet forrás
├── 06b-week_prozo.md           # 6.5 esettanulmány forrás (prozopográfia)
├── 08-week8.md                 # 8. fejezet forrás
├── 08b-week_nsz.md             # 8.5 esettanulmány forrás (NSZ szövegbányászat)
├── _bookdown.yml               # Bookdown konfiguráció (fejezetek sorrendje)
├── _output.yml                 # Output formátumok (GitBook, PDF, EPUB)
├── references.bib              # Bibliográfia
├── style.css                   # Egyéni stílusok
├── images/
│   └── cover.jpg               # Borítókép
├── libs/                       # GitBook és egyéb JS/CSS könyvtárak
└── *.html                      # Kompilált HTML (GitHub Pages-re kerül)
```

---

## Licenc

A könyv tartalma a [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) licenc alatt érhető el.
