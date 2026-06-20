# Salon WP — Ilse Aesthetics (AGENTS)

> Cursor: lasi šo failu **un** `docs/PROJECT.md` + **`docs/WP-LOCAL.md`** + `docs/HANDOFF.md` katra sesijas sākumā.

## Projekts vienā rindkopā

**Ilse Aesthetics** — estētikas salons Augsburgā (DE). Šis repo ir **plānošana + nākotnes WP kods**, ne visa WordPress instalācija. Sadarbība: Ilze (Windows) plāno, Eduards (Mac) review un vēlāk kodē.

## Lomas

| Kas | Kur | Ko dara |
|-----|-----|---------|
| **Ilze** | `plan/`, `docs/HANDOFF.md` | Sitemap, pakalpojumi, DE teksti, backlog |
| **Eduards** | `src/` + review | Monitorē `plan/`; WP kods vēlāk |
| **Kopīgi** | `docs/HANDOFF.md` | Statuss starp Mac un Windows |

**Čats = sesija. Patiesība = Git.**

## Ilze — aģenta noteikumi

1. **Rediģē TIKAI** `plan/` un `docs/HANDOFF.md`
2. **NEaiztikt** `src/`, WP, spraudņus, konfigurāciju
3. **Valoda**: viss publicējamais saturs — **vāciski (DE)**
4. **Stils**: Quiet Luxury — profesionāls, mierīgs, ekskluzīvs; bez pārspīlēta marketinga
5. **Biznesa noteikumi** tekstos: tikai ar pierakstu; konsultācija 50€; atcelšana 24h / 35€ Ausfallgebühr
6. Pēc izmaiņām: atjaunini `HANDOFF.md`, commit tikai `plan/` + HANDOFF

## Eduards — aģenta noteikumi

1. Sākumā: lasīt `plan/`, nekodēt bez prasības
2. Implementācija tikai `src/` pēc plāna apstiprināšanas
3. Merge `plan` → `main` tikai kad plāns pārskatīts

## Mapes

| Mape | Saturs |
|------|--------|
| `plan/sitemap.md` | Lapu koks |
| `plan/services.md` | Pakalpojumi + cenas (melnraksts) |
| `plan/pages/` | Lapu teksti DE pirms WP |
| `plan/backlog.md` | Uzdevumi, prioritātes |
| `docs/HANDOFF.md` | Kas darīts / kas tālāk |
| `docs/PROJECT.md` | Sadarbības repo konteksts (lasāms, nemainīt Ilzei) |
| **`docs/WP-LOCAL.md`** | **Mac WP** — kas jau izstrādāts (lapas, pakalpojumi, theme) |
| `src/` | WP custom — vēlāk, Eduards |

## Zari

- `plan` — Ilze strādā šeit
- `main` — apstiprināts plāns + kods

## Kontakti (salons)

- Adrese: Herrenbachstraße 25c, 86161 Augsburg
- Tel: +49 179 1539912
- E-pasts: aesthetics@ilseaesthetics.com
- Stundas: Mo–Fr 10–19

## GitHub

`git@github.com:yanko0987/salon-wp.git` · Windows: `C:\Projects\salon-wp`

## Sesijas sākums (aģentam)

```
1. Lasīt docs/HANDOFF.md      → kas jaunākais
2. Lasīt docs/PROJECT.md      → sadarbības repo
3. Lasīt docs/WP-LOCAL.md     → Mac WP (kas jau uzbūvēts)
4. Skatīt plan/backlog.md     → kas jādara
5. Strādāt tikai atļautajās mapēs
```
