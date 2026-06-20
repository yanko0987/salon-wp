# Salon WP (Vācija)

Sadarbības repozitorijs: Ilze plāno, Eduards implementē.

| Kas | Kur | Ko dara |
|-----|-----|---------|
| **Ilze** | tikai `plan/` | **Virzība** + **mārketings** (ne WP, ne cenas) |
| **Eduards** | `src/` + review | Sākumā skatās `plan/` commitus; vēlāk WP kods |
| **Kopīgi** | `docs/HANDOFF.md` | Īss statuss (čati nesinhronizējas Mac/Windows) |

**Čats = sesija. Patiesība = Git.**

## Struktūra

```
salon-wp/
├── README.md
├── AGENTS.md
├── plan/          ← TIKAI ILZE
├── docs/
│   └── HANDOFF.md
└── src/           ← EDUARDS (vēlāk WP custom)
```

## Dokumentācija

| Fails | Kam |
|-------|-----|
| [docs/SETUP.md](docs/SETUP.md) | Uzstādīšana Mac + Windows |
| [docs/PROJECT.md](docs/PROJECT.md) | Pilns projekta konteksts (aģentam) |
| `docs/WP-LOCAL.md` | **Mac WP** — kas jau izstrādāts (lapas, pakalpojumi, theme) |
| `docs/HANDOFF.md` | Aktuālais statuss |

**Ilze (Windows):** atver `C:\Projects\salon-wp` — aģents zina visu projektu caur `AGENTS.md` + `PROJECT.md`.
