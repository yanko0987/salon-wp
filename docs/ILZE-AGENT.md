# Ilzes aģents — instrukcijas

> Čats: **Ilze — plāns** · Mape: `C:\Projects\salon-wp` · Zars: **`plan`**

Ilze plāno **tikai virzību un mārketingu** — ne WP, ne cenas, ne lapas.

---

## Divas komandas

| Komanda | Kad lietot | Ko dara |
|---------|------------|---------|
| **`/sakārto vidi`** | Pirmā reize, ja kaut kas nestrādā, pēc clone | Pārbauda mapi, zaru, Git, failus |
| **`/atjauno profilu`** | Katras sesijas sākumā | `git pull` + ielādē kontekstu + kopsavilkums |

---

## `/sakārto vidi`

**Mērķis:** pārliecināties, ka Windows vide ir pareiza pirms darba.

### Aģents dara (secīgi)

1. **Pārbauda mapi** — jābūt `C:\Projects\salon-wp` (ne OneDrive).
2. **Ja mapes nav** — dod lietotājam:
   ```powershell
   New-Item -ItemType Directory -Path C:\Projects -Force
   cd C:\Projects
   git clone git@github.com:yanko0987/salon-wp.git
   cd salon-wp
   git checkout plan
   ```
3. **Pārbauda Git zaru** — lietotājam jāpalaiž:
   ```powershell
   cd C:\Projects\salon-wp
   git checkout plan
   git status
   ```
   Jābūt: `On branch plan`, working tree clean (vai skaidri redzamas tikai Ilzes izmaiņas).
4. **Pārbauda obligātos failus:**
   - `plan/direction.md`
   - `plan/marketing.md`
   - `plan/backlog.md`
   - `docs/HANDOFF.md`
   - `AGENTS.md`
5. **Atgādina lomas robežas:**
   - Rediģēt: `direction.md`, `marketing.md`, `marketing/`, `backlog.md`, `HANDOFF.md`
   - **Nerediģēt:** `sitemap.md`, `services.md`, `src/`, WP, tehnika
6. **Beigu ziņojums** — īss checklist ✅/❌:

```
✅ Mape: C:\Projects\salon-wp
✅ Zars: plan
✅ Faili: direction, marketing, backlog, HANDOFF
✅ Loma: virzība + mārketings
→ Nākamais solis: /atjauno profilu
```

---

## `/atjauno profilu`

**Mērķis:** ņemt svaigāko no Git un ielādēt pilnu projekta kontekstu sesijai.

### Aģents dara (secīgi)

1. **Lūdz lietotājam** (vai palaid, ja terminal pieejams):
   ```powershell
   cd C:\Projects\salon-wp
   git checkout plan
   git pull origin plan
   ```
2. **Izlasa failus** (secībā):
   - `docs/HANDOFF.md` — kas jaunākais
   - `AGENTS.md` — lomas
   - `docs/PROJECT.md` — projekts
   - `docs/WP-LOCAL.md` — Mac WP (konteksts, **nemainīt**)
   - `plan/backlog.md` — kas jādara
   - `plan/direction.md` — pašreizējais stāvoklis
   - `plan/marketing.md` — pašreizējais stāvoklis
3. **Kopsavilkums lietotājam** (vienmēr šajā formātā):

```
## Profils atjaunināts

**Pēdējais HANDOFF:** (1–2 teikumi)
**Ilzes fokuss:** virzība + mārketings (DE, Quiet Luxury)
**Backlog P1:** (saraksts no backlog.md)
**Ko NE darīt:** WP, cenas, sitemap, services

Gatava strādāt. Ko sākam?
```

4. **Nesāc rediģēt failus**, kamēr Ilze nepasaka konkrētu uzdevumu.

---

## Ilzes ikdienas rutīna

```
1. Atver Cursor → C:\Projects\salon-wp
2. /sakārto vidi        (ja pirmā reize vai problēma)
3. /atjauno profilu     (katras sesijas sākumā)
4. Strādā ar direction / marketing
5. Atjaunina HANDOFF.md
6. git add plan/ docs/HANDOFF.md
   git commit -m "..."
   git push origin plan
```

---

## Piemēru uzdevumi pēc profila atjaunošanas

- „Palīdzi aizpildīt `direction.md` — mērķauditorija”
- „5 Instagram tēmas DE → `plan/marketing/instagram-q3.md`”
- „Atjaunini `marketing.md` — vasaras fokuss Körper”

---

## Kad kaut kas no Edvarda Mac

Eduards redz tavas izmaiņas caur:
- `git push` → viņš `git pull` / GitHub Commits
- `docs/HANDOFF.md` — īss statuss

Ja vajag kaut ko vietnē — raksti **`direction.md` → „Piezīmes Eduardam”**, ne WP.
