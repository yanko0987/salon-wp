# Aģentu komandas — Ilze un Eduards

> Abām pusēm: **`/sakārto vidi`** un **`/atjauno profilu`**
> Čats = sesija. Patiesība = Git + `docs/HANDOFF.md`.

---

## Divas komandas (kopīgas)

| Komanda | Kad | Ko dara |
|---------|-----|---------|
| **`/sakārto vidi`** | Pirmā reize, pēc clone, ja kaut kas nestrādā | Pārbauda mapi, zaru, Git, obligātos failus |
| **`/atjauno profilu`** | **Katras sesijas sākumā** | Sync no Git + **apkopo padarīto un atlikušo** |

> **`/atjauno profilu` nav tikai `git pull`.** Galvenais — statusa kopsavilkums: kas jau ir, kas vēl jāizdara.

---

# ILZE (Windows)

Mape: `C:\Projects\salon-wp` · Zars: **`plan`**
Fokuss: **virzība + mārketings** — ne WP, ne cenas, ne lapas.

## `/sakārto vidi` — Ilze

1. Mape = `C:\Projects\salon-wp` (ne OneDrive)
2. Ja nav — clone:
   ```powershell
   New-Item -ItemType Directory -Path C:\Projects -Force
   cd C:\Projects
   git clone git@github.com:yanko0987/salon-wp.git
   cd salon-wp
   git checkout plan
   ```
3. Pārbauda:
   ```powershell
   cd C:\Projects\salon-wp
   git checkout plan
   git status
   ```
4. Obligātie faili: `plan/direction.md`, `plan/marketing.md`, `plan/backlog.md`, `docs/HANDOFF.md`, `AGENTS.md`
5. Checklist ✅/❌ → „Nākamais: `/atjauno profilu`”

## `/atjauno profilu` — Ilze

### 1. Sync
```powershell
cd C:\Projects\salon-wp
git checkout plan
git pull origin plan
```

### 2. Izlasi
- `docs/HANDOFF.md`
- `plan/backlog.md` — `[x]` vs `[ ]`
- `plan/direction.md` — aizpildītās vs tukšās sadaļas
- `plan/marketing.md` — tāpat
- `plan/marketing/` — jauni faili
- `git log --oneline -5` — pēdējie commiti

### 3. Atbilde — **vienmēr šis formāts**

```markdown
## Profils atjaunināts

### ✅ Padarīts
- (HANDOFF + pēdējie commiti)
- (backlog [x] punkti)
- (aizpildītas sadaļas direction.md / marketing.md)
- (faili plan/marketing/ ja ir)

### 📋 Atlikušais
- (backlog [ ] — P1 vispirms)
- (tukšas sadaļas direction / marketing)
- (HANDOFF „kas tālāk”)

### 🎯 Fokuss šai sesijai
Virzība + mārketings · DE · Quiet Luxury
Ko **nedarīt**: WP, cenas, sitemap, services

Ko sākam?
```

**Nerediģē failus**, kamēr Ilze nedod konkrētu uzdevumu.

---

# EDUARDS (Mac)

Repozitorijs: `~/Projects/salon-wp` · WP: `/Applications/MAMP/htdocs/wp-local`
Fokuss: review Ilzes plāna + Mac WP implementācija.

## `/sakārto vidi` — Eduards

1. **`salon-wp` repo:**
   ```bash
   cd ~/Projects/salon-wp
   git remote -v
   git branch -vv
   git status
   ```
2. **`wp-local` (Mac WP):**
   - Ceļš: `/Applications/MAMP/htdocs/wp-local`
   - URL: `http://localhost:8888/wp-local`
   - PHP: `/Applications/MAMP/bin/php/php8.1.31/bin/php`
3. Obligātie faili `salon-wp`: `docs/HANDOFF.md`, `docs/WP-LOCAL.md`, `plan/`, `AGENTS.md`
4. Checklist ✅/❌ → „Nākamais: `/atjauno profilu`”

## `/atjauno profilu` — Eduards

### 1. Sync
```bash
cd ~/Projects/salon-wp
git fetch origin
git checkout plan
git pull origin plan
```

### 2. Izlasi + analizē
- `docs/HANDOFF.md`
- `git log origin/plan --oneline -10`
- `git diff main..plan -- plan/ docs/HANDOFF.md` (ja main atpaliek)
- `plan/backlog.md`, `direction.md`, `marketing.md`, `plan/marketing/`
- `docs/WP-LOCAL.md` — Mac WP konteksts
- Ja vajag: `docs/ilse behandlungen.md` wp-local (Eduards implementācijai)

### 3. Atbilde — **vienmēr šis formāts**

```markdown
## Profils atjaunināts

### ✅ Padarīts (Ilze / plan)
- (commiti + HANDOFF)
- (kas aizpildīts direction / marketing)
- (backlog [x])

### 📋 Atlikušais (Ilze)
- (backlog [ ] — ko viņai vēl lūgt)

### 🔧 Tava puse (Eduards)
- (ko implementēt Mac WP pēc „Piezīmes Eduardam”)
- (src/ / WP atvērtie uzdevumi)

### 🖥 Mac WP īsumā
- (1–2 teikumi no WP-LOCAL — fāze, blockers)

### 🔄 Git
- plan HEAD: (commit hash + ziņa)
- Nesinhronizēts ar main: (jā / nē)

Ko darām tālāk?
```

---

## Ikdienas rutīna

**Ilze:** `/atjauno profilu` → strādā → HANDOFF → commit → push

**Eduards:** `/atjauno profilu` → redz Ilzes padarīto → implementē / atgriež feedback → merge kad OK

---

## Commit + HANDOFF (Ilze pēc darba)

```powershell
git add plan/ docs/HANDOFF.md
git commit -m "Mārketings: (ko tieši)"
git push origin plan
```

HANDOFF vienmēr atjaunina — tā Eduards redz bez `git diff`.
