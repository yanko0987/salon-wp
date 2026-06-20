# Salon WP — Ilse Aesthetics (AGENTS)

> Cursor: lasi šo failu **un** `docs/PROJECT.md` + **`docs/WP-LOCAL.md`** + `docs/HANDOFF.md` katra sesijas sākumā.

## Projekts vienā rindkopā

**Ilse Aesthetics** — estētikas salons Augsburgā (DE). Ilze (Windows) plāno **fizisko virzību un mārketingu**. Eduards (Mac) uztur WP, tehniku un implementāciju.

## Lomas

| Kas | Kur | Ko dara |
|-----|-----|---------|
| **Ilze** | `plan/` | **Virzība** (`direction.md`), **mārketings** (`marketing.md`, `marketing/`), backlog |
| **Eduards** | `src/` + Mac WP | Vietne, pakalpojumi, cenas, tehnika — skatīt `docs/WP-LOCAL.md` |
| **Kopīgi** | `docs/HANDOFF.md` | Statuss starp Mac un Windows |

**Čats = sesija. Patiesība = Git.**

## Ilze — aģenta noteikumi

1. **Rediģē TIKAI** `plan/` (galvenokārt `direction.md`, `marketing.md`, `marketing/`, `backlog.md`) un `docs/HANDOFF.md`
2. **Fokuss**: salona virzība, mērķauditorija, mārketings, Instagram ziņas — **ne** WP, ne tehniskās lapas, ne cenu sinhronizācija
3. **NEaiztikt** `src/`, WP, spraudņus; **neaizpildīt** `sitemap.md` / `services.md` (tās uztur Eduards)
4. **Valoda**: publicējamais saturs — **vāciski (DE)**
5. **Stils**: Quiet Luxury — profesionāls, mierīgs, ekskluzīvs
6. Ja vajag ko vietnē — raksti sadaļā „Piezīmes Eduardam” `direction.md`, neimplementē pats
7. Pēc izmaiņām: atjaunini `HANDOFF.md`, commit tikai `plan/` + HANDOFF

## Eduards — aģenta noteikumi

1. Lasīt Ilzes `plan/direction.md` un `plan/marketing.md` pirms WP izmaiņām
2. Tehnika: Mac `wp-local`, `src/`, Amelia, lapas — skatīt `WP-LOCAL.md`
3. Merge `plan` → `main` kad stratēģija pārskatīta

## Mapes (Ilze)

| Mape | Saturs |
|------|--------|
| `plan/direction.md` | Fiziskā virzība, vīzija, mērķauditorija |
| `plan/marketing.md` | Ziņas, kanāli, Instagram virzība |
| `plan/marketing/` | Konkrēti mārketinga uzdevumi / melnraksti |
| `plan/backlog.md` | Prioritātes |
| `plan/sitemap.md` | Atsauce (Eduards) — Ilze nelasa kā darbu |
| `plan/services.md` | Atsauce (Eduards) — Ilze nelasa kā darbu |
| `docs/WP-LOCAL.md` | Mac WP — lasāms kontekstam, nemainīt |

## Zari

- `plan` — Ilze strādā šeit
- `main` — apstiprināts + kods

## Kontakti (salons)

- Adrese: Herrenbachstraße 25c, 86161 Augsburg
- Tel: +49 179 1539912
- E-pasts: aesthetics@ilseaesthetics.com
- Stundas: Mo–Fr 10–19

## GitHub

`git@github.com:yanko0987/salon-wp.git` · Windows: `C:\Projects\salon-wp`

## Sesijas sākums (Ilzes aģentam)

```
1. docs/HANDOFF.md
2. docs/PROJECT.md + docs/WP-LOCAL.md (konteksts, ne Ilzes rediģēšana)
3. plan/backlog.md
4. Strādāt: direction.md, marketing.md, marketing/
```
