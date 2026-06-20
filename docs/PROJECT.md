# Projekta konteksts — Ilse Aesthetics (salon-wp)

> **Šis fails ir lasāms visiem.** Ilze to nerediģē — tas dod aģentam pilnu projekta bildi, pat ja strādā tikai `plan/`.

## Kas tas ir

**Ilse Aesthetics** — estētikas salons Augsburgā, Vācijā. Šis repozitorijs (`salon-wp`) ir **plānošanas un nākotnes WP koda** sadarbības vieta starp Ilzi un Eduardu. Tas **nav** visa WordPress instalācija — tikai plāns + vēlāk custom kods `src/`.

| Lauks | Vērtība |
|-------|---------|
| **Nosaukums** | Ilse Aesthetics |
| **Īpašniece** | Ilze |
| **Adrese** | Herrenbachstraße 25c, 86161 Augsburg, DE |
| **Tālrunis** | +49 179 1539912 |
| **E-pasts** | aesthetics@ilseaesthetics.com |
| **Darba laiks** | Mo–Fr 10–19 Uhr (citi laiki pēc pieprasījuma) |
| **Vietnes valoda** | vāciski (DE) |
| **Stils** | Quiet Luxury — profesionāls, mierīgs, ekskluzīvs |

## Biznesa noteikumi (obligāti tekstos)

- **Tikai ar pierakstu** — spontāni apmeklējumi netiek pieņemti
- **Konsultācija**: 50 EUR (pilnībā ieskaitāma procedūrā)
- **Atcelšana**: vismaz 24h iepriekš; citādi Ausfallgebühr 35 EUR
- **Abonementi**: 6/8/10 paketes, priekšapmaksa, derīgums 6 mēneši, nav atmaksas par neizmantotajām

## Pakalpojumu kategorijas (plānošanai)

| Kategorija | Piemēri |
|------------|---------|
| **Gesicht** | Aqua Facial, Microneedling, RF-Lifting, Chemische Peelings, Mesotherapie |
| **Körper** | Bodyforming, Klassische Massage, Relax Massage |
| **Haare** | Haar-Mesotherapie |
| **Augen** | Wimpernlifting |

Detalizētas cenas, lapas, WP — **Eduards** (`docs/WP-LOCAL.md`). Ilze plāno **virzību un mārketingu** (`plan/direction.md`, `plan/marketing.md`).

## Repozitorija struktūra

```
salon-wp/
├── AGENTS.md              ← aģenta galvenais konteksts (Cursor lasa automātiski)
├── README.md
├── plan/                  ← ILZE: plāns, DE teksti, backlog
│   ├── sitemap.md
│   ├── services.md
│   ├── pages/
│   └── backlog.md
├── docs/
│   ├── PROJECT.md         ← sadarbības repo
│   ├── WP-LOCAL.md        ← Mac WP stāvoklis (kas jau gatavs)
│   ├── HANDOFF.md         ← aktuālais statuss abiem
│   └── SETUP.md           ← uzstādīšana Mac/Windows
├── src/                   ← EDUARDS: WP custom kods (vēlāk, tukšs)
└── .cursor/rules/         ← Cursor noteikumi
```

## Lomas un zari

| Kas | Zars | Mapes | Ko dara |
|-----|------|-------|---------|
| **Ilze** (Windows) | `plan` | `direction.md`, `marketing.md` | Virzība + mārketings |
| **Eduards** (Mac) | `main` + review | `src/`, Mac WP | Vietne, tehnika, pakalpojumi |
| **Kopīgi** | — | `docs/HANDOFF.md` | Īss statuss — čati nesinhronizējas |

**Čats = sesija. Patiesība = Git + HANDOFF.**

## Darba plūsma

### Ilze (katru sesiju)
1. `git pull` (pirms darba)
2. Lasīt `docs/HANDOFF.md` — kas jau darīts
3. Rediģēt `plan/` (DE teksti)
4. Atjaunināt `docs/HANDOFF.md`
5. `git add plan/ docs/HANDOFF.md` → commit → `git push`

### Eduards
1. `git fetch` → skatīt `plan` zaru
2. Kad plāns OK → `merge plan` uz `main`
3. WP kods tikai `src/` — ne visa WP instalācija šeit

## Tehniskais (vēlāk, ne Ilzei)

- **Stack**: WordPress + WooCommerce (WoodMart) — implementācija Mac pusē
- **Produkcija**: atsevišķa WP instalācija Mac — **`docs/WP-LOCAL.md`** apraksta visu, kas jau ir uzbūvēts
- **Šis repo**: plāns + custom theme/plugin fragments `src/`

## Fāze tagad

**Fāze 1 — Plānošana.** Ilze aizpilda `sitemap.md`, `services.md`, `backlog.md`, `pages/`. Kods vēl nav.

## GitHub

- **Repo**: `git@github.com:yanko0987/salon-wp.git` (privāts)
- **Windows ceļš**: `C:\Projects\salon-wp`
- **Mac ceļš**: `~/Projects/salon-wp`
