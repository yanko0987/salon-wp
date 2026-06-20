# Mac WP — lokālā izstrāde (atsauce Ilzes aģentam)

> **Šis fails ir lasāms, nemaināms Ilzei.** Apraksta WordPress, kas **jau izstrādāts** Eduarda Mac datorā. Ilzei **nav** piekļuves šim kodam — tikai šī dokumentācija caur Git.

## Kur tas atrodas

| | |
|---|---|
| **Dators** | Eduards — Mac (MAMP) |
| **Ceļš** | `/Applications/MAMP/htdocs/wp-local` |
| **URL** | `http://localhost:8888/wp-local` |
| **Nav** | Windows, nav `salon-wp` repozitorijā |

**Plūsma:** Ilze plāno `plan/` → Eduards implementē / sinhronizē Mac WP → produkcija vēlāk.

---

## Tehniskais stack

| Komponente | Kas |
|------------|-----|
| **CMS** | WordPress (latest stable) |
| **Tēma** | Hello Elementor + **`ilse_custom`** child theme |
| **Lapu būvētājs** | Elementor (lapas ar manuāli labotiem linkiem) |
| **Pieraksti** | Amelia (`amelia_services` — cenu avots) |
| **Valoda** | vāciski (DE) |
| **Stils** | Quiet Luxury — zelts `#D4AF37`, neitrāli toņi |

### Child theme `ilse_custom` (jau izveidots)

```
wp-content/themes/ilse_custom/
├── functions.php          # GDPR fonts, blog AJAX, registry
├── core/
│   ├── styles-global.php  # @font-face, globālie stili
│   └── registry.php       # asset / shortcode reģistrs
├── parts/
│   ├── hero.php
│   ├── categories-grid.php
│   ├── treatments-grid.php
│   ├── blog-grid.php / blog-archive.php
│   ├── founder-section.php
│   ├── trust-bar.php
│   ├── cta-banner.php
│   ├── instagram-ribbon.php
│   └── transparency-registry.php
├── header/ footer/
└── assets/fonts/          # Playfair, Montserrat, Outfit (lokāli, GDPR)
```

Papildus `hello-elementor/ilse_custom/` — breadcrumbs, prices, category-card, Instagram cache.

---

## Galvenās lapas (WordPress, lokāli)

| Lapa | page_id | Piezīmes |
|------|---------|----------|
| **Behandlungen** (pakalpojumi) | 82 | Galvenā kataloga lapa; apakšsadaļas Gesicht/Körper/Haare |
| **Über uns** | 84 | Stila etalons (Brand Style Book) |
| **Aqua Facial** | 1571 | Atsevišķa procedūras lapa |
| **Chemische Peelings** | 1854 | |
| **Mesotherapie Gesicht** | 1885 | |
| **Medizinisches Microneedling** | 2614 | |
| **Fraktioniertes RF-Lifting** | 2635 | |
| **Wimpernlifting** | 2823 | |
| **Digital Transparency** | — | `/digital-transparency/` — AI/asset reģistrs |
| **Blog** | — | Filtrs, featured post, Quiet Luxury layout |

> Konkrēti slug un permalink var atšķirties; `page_id` ir stabilāks atsauces punkts Mac WP.

---

## Pakalpojumi (kā jau ir Mac WP)

Avots: `internal/data/knowledge_base.json` + `docs/ilse behandlungen.md` (Mac).

| Pakalpojums | Ilgums | Cena (no) | page_id |
|-------------|--------|-----------|---------|
| Aqua Facial | 45–60 min | 89–140 € | 1571 |
| Medizinisches Microneedling | 20 min | 139 € | 2614 |
| Fraktioniertes RF-Lifting | 60 min | ab 249 € | 2635 |
| Radiofrequenz (ohne Nadeln) | 20 min | ab 59 € | 82 |
| Chemische Peelings | 30 min | 79 € | 1854 |
| Mesotherapie Gesicht | 30 min | 150–329 € | 1885 |
| Haar-Mesotherapie | 20–30 min | 129–199 € | 82#haare |
| Bodyforming | 30–80 min | Probe 75 €; Pakete ab 495 € | 82#koerper |
| Klassische Massage | 30 min | ab 39 € | 82#koerper |
| Relax Massage | 30–45 min | ab 49 € | 82#koerper |
| Wimpernlifting | 45–60 min | 59 € | 2823 |

**Cenu noteikumi Mac WP:** Amelia DB = avots; vietnē apaļoti integer (piem. 89€). Ilze `plan/services.md` raksta melnrakstu — Eduards sinhronizē.

---

## Biznesa loģika (jau iekodēta / dokumentēta)

- **Nur mit Termin** — bez pieraksta nav
- **Beratung** 50 € — ieskaitāma procedūrā
- **Stornierung** — 24h; citādi Ausfallgebühr 35 €
- **Abonnements** — 6/8/10 paketes, 6 mēneši, priekšapmaksa

---

## Kas jau izdarīts Mac WP (2026.04+)

| Joma | Status |
|------|--------|
| **Quiet Luxury dizains** | Hero, grid, footer, tipogrāfija |
| **GDPR** | Lokālie fonti; bez Google Fonts; bez Unsplash |
| **EMS-VAHOS** | Asset licencēšana, `ai-transparency.json` |
| **Transparency lapa** | `/digital-transparency/` |
| **Instagram lente** | Manuāla sinhronizācija (nav cron) |
| **Media Library** | Restaurācija pēc incidenta — **Manual First** |
| **Blog** | AJAX filtrs, featured layout |

---

## ⚠️ INTEGRITY SHIELD — ko Ilzes aģents NEDRĀK

Mac WP ir trausls pēc 2026.04 Media Library incidenta. **Ilze / viņas aģents:**

- **NE** piedāvā DB izmaiņas, search-replace, failu pārdēvēšanu uploads/
- **NE** dzēš “orphan” failus
- **NE** normalizē failu casing
- Plānošanā **respektē**, ka Elementor linki ir **manuāli** laboti

Ja `plan/` ierosina satura izmaiņas — tas ir **melnraksts**; Eduards ievieš Mac WP.

---

## Avoti patiesībai (tikai Mac — Eduards)

| Fails | Saturs |
|-------|--------|
| `docs/ilse behandlungen.md` | Pilni procedūru apraksti DE |
| `internal/data/knowledge_base.json` | Pakalpojumi, FAQ, kontakti |
| `docs/BRAND_STYLE_BOOK.md` | Tipogrāfija, krāsas, Elementor noteikumi |
| `ai-transparency.json` | Vizualo aktīvu reģistrs |
| `ANTIGRAVITY.md` | Projekta atmiņa, Integrity Shield |

Ilze tos **neredz** — bet `plan/` saturam jābūt saderīgam. Ja šaubas — raksti `docs/HANDOFF.md` un jautā Eduardam.

---

## Sinhronizācija: plan/ ↔ Mac WP

```
Ilze (plan/)  →  git push plan  →  Eduards review  →  Mac WP + src/
                      ↑                                    ↓
                 HANDOFF.md  ←────────── statuss ──────────┘
```

| Ilze dara | Eduards dara |
|-----------|--------------|
| `plan/services.md` melnraksts | Salīdzina ar `ilse behandlungen.md` |
| `plan/pages/*.md` teksti DE | Ieliek Elementor / theme |
| `plan/sitemap.md` | Pārbauda pret esošajām lapām (page_id) |
| `plan/backlog.md` | Prioritizē implementāciju |

---

## Kontakti (salons — jau WP)

- **Adrese:** Herrenbachstraße 25c, 86161 Augsburg
- **Tel:** +49 179 1539912
- **E-pasts:** aesthetics@ilseaesthetics.com
- **Stundas:** Mo–Fr 10–19 Uhr
