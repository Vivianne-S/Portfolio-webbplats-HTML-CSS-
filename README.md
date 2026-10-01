# Portfolio-webbplats (HTML & CSS)

Personlig portfolio för **Vivianne Sonnerborg**, webb- och apputvecklare i Göteborg.
Webbplatsen är byggd som slutuppgift i HTML5 och CSS: semantisk struktur, Flexbox,
CSS Grid, mobil-först och tillgänglighet.

**Målgrupp:** rekryterare, lärare och uppdragsgivare som snabbt vill se vem jag är,
vad jag kan och hur de når mig.

Färgtemat är hämtat från [vivianne-sonnerborg.se](https://www.vivianne-sonnerborg.se):
mörk bakgrund, neonrosa/lila accenter och ljus text.

## Kör lokalt

1. Ladda ner eller packa upp projektet.
2. Öppna `index.html` i en webbläsare (dubbelklicka, eller dra filen till fönstret).

Vill du ha en lokal server (rekommenderas så att sökvägar och bilder beter sig
som på webben):

```bash
cd sökväg/till/projektet
python3 -m http.server 8765
```

Öppna sedan [http://127.0.0.1:8765/index.html](http://127.0.0.1:8765/index.html).

Publicerad länk saknas i denna version. Se *Kända brister*.

## Mappstruktur

Inlämningen följer zip-kravet (`/css/` och `/assets/`), inte exempelnamnet `/styles`.
HTML länkar fyra stilmallar i ordning (utan `@import`, som kan strula i vissa webbläsare):

```
.
├── index.html
├── projects.html
├── about.html
├── contact.html
├── css/
│   ├── variables.css    Färger, typografi, avstånd
│   ├── base.css         Reset, rubriker, fokus, skip-länk
│   ├── layout.css       Header, meny, footer, brytpunkter
│   ├── components.css   Hero, projekt, hobbyer, formulär
│   └── styles.css       Samma regler samlade i en fil (översikt)
├── assets/images/       SVG-illustrationer och favicon
└── README.md
```

## Hur kraven är uppfyllda

### 1. Struktur och semantik

- [x] Fyra HTML-sidor: `index.html`, `projects.html`, `about.html`, `contact.html`
- [x] Landmärken på varje sida: `header`, `nav`, `main`, `section`, `article`, `footer`
- [x] En `h1` per sida, därefter `h2`/`h3` i logisk hierarki

### 2. Layout

- [x] **Flexbox:** header/nav, startsidans hero och *Min väg*, Om mig (*På fritiden*, *Vad jag gör*), kontaktlayout och formulärrad
- [x] **CSS Grid:** projektkorten i `.projects` (1 kolumn → 2 → 6 spår där Spelinsikt spänner 4 kolumner)
- [x] Tydliga class-namn (`project`, `featured-project`, `header-bar`)

### 3. Responsivitet

- [x] Mobil-först
- [x] Brytpunkter **480px**, **768px**, **1024px** och **1280px**
- [x] Bilder med `max-width: 100%`, `width`/`height` i HTML och lätta SVG:er (ca 0,5–3 kB)

### 4. Typografi och färg

- [x] Rubrikstorlekar för `h1`–`h3`, `line-height` 1,6 på brödtext och 1,2 på rubriker
- [x] Kontrast mot `#030014` (WCAG AA eller högre), till exempel:
  - text `#f5f7ff` ≈ 19,4:1
  - muted `#a8adc4` ≈ 9,3:1
  - rosa `#ff2bd6` ≈ 6,5:1
  - vit på knapp `#a21caf` ≈ 6,3:1

### 5. Tillgänglighet

- [x] Beskrivande `alt` på alla bilder
- [x] Beskrivande länkar (inte “klicka här”), t.ex. *Öppna HomeFit på GitHub*
- [x] Skip-länk *Hoppa till innehållet*
- [x] Tydlig cyan fokusram (`:focus-visible`) för tangentbordsnavigering
- [x] `aria-current="page"` i menyn, `aria-label` på `nav`

### 6. Formulär

- [x] Kontaktsida med namn, e-post och meddelande
- [x] `label` kopplad via `for`/`id`, `required` och `type="email"`

### 7. Publicering / körning

- [x] Körinstruktion i denna README (se ovan)

### 8. Kvalitet

- [x] Inga brutna interna länkar
- [x] Logisk mappstruktur
- [x] Optimerade SVG-bilder
- [x] Ingen oanvänd CSS-klass

### 9. Kodvalidering

Validerat 2026-09-30:

| Verktyg | Resultat |
|---|---|
| [W3C HTML](https://validator.w3.org/) | **0 errors** på alla fyra sidor |
| [W3C CSS](https://jigsaw.w3.org/css-validator/) | **0 errors** på alla stilmallar |

**Warnings som kan ignoreras:** CSS-validatorn varnar *“Due to their dynamic nature, CSS variables are currently not statically checked”*. Det är en begränsning i validatorn, inte fel i koden. Custom properties (`var(--…)`) är giltig CSS och används medvetet i `:root`.

## Kända brister / att-göra

- Webbplatsen är inte publicerad på Netlify ännu.
- Formuläret använder `mailto:` och öppnar användarens e-postprogram. Det kräver ingen server, men fungerar sämre om besökaren saknar e-postklient.
- Illustrationerna är stiliserade, inte skärmdumpar från apparna. Nala och familjen är också ritade, inte foton.

## För den muntliga redovisningen (6–7 min)

1. Navigera Start → Projekt → Om mig → Kontakt.
2. Dra i fönstret och stanna vid **480px**, **768px**, **1024px** och **1280px** (meny, hero, projektgrid, hobbykort).
3. **Flexbox:** t.ex. hero eller *Min väg* på startsidan — kolumn på mobil, rad på desktop.
4. **CSS Grid:** `.projects` på Projektsidan — 1 kolumn, 2 kolumner, sedan 6 spår där Spelinsikt (`.featured-project`) spänner över fyra (`grid-column: 1 / 5`).
5. Tabba från adressfältet: skip-länk, meny, knappar; peka på cyan fokus och en `alt`-text i inspektören.
