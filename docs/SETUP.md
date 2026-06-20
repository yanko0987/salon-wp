# Uzstādīšana — soli pa solim

## 0. Pirms sākuma

- **Mape**: lokāli, ne OneDrive (permission problēmas)
- **Ceļš**: `~/Projects/salon-wp` (Mac) vai `C:\Projects\salon-wp` (Windows)
- **Cursor**: atsevišķi čati — `Ilze — plāns` un `Eduards — review`

---

## 1. Eduards (Mac) — jau izdarīts

```bash
cd ~/Projects/salon-wp
git init
git branch -M main
git checkout -b plan
```

Struktūra, `.gitignore`, `AGENTS.md`, Cursor rules — gatavi.

---

## 2. GitHub (privāts repo)

1. GitHub → **New private repository** → nosaukums: `salon-wp`
2. **Ne** pievieno README (jau ir lokāli)

```bash
cd ~/Projects/salon-wp
git add .
git commit -m "Initial: plan/ for Ilze, dev scaffold"
git remote add origin git@github.com:USER/salon-wp.git   # aizstāj USER
git push -u origin plan
git push -u origin main
```

---

## 3. Ilze (Windows) — clone un darbs

```powershell
cd C:\Projects
git clone git@github.com:USER/salon-wp.git
cd salon-wp
git checkout plan
```

### Cursor

1. **File → Open Folder** → `C:\Projects\salon-wp`
2. Jauns čats: **Ilze — plāns**
3. Rediģē tikai `plan/` un `docs/HANDOFF.md`

### Darba cikls

```powershell
# pēc izmaiņām plan/
git add plan/ docs/HANDOFF.md
git commit -m "Plāns: pakalpojumu saraksts"
git push
```

Atjaunini `docs/HANDOFF.md` — kas mainīts, kas tālāk.

---

## 4. Eduards — monitorēšana (bez merge)

```bash
cd ~/Projects/salon-wp
git fetch
git log plan --oneline -5
git diff main..plan -- plan/
```

Vai GitHub → **Commits** uz `plan` zaru.

**Merge uz `main` tikai tad**, kad plāns apstiprināts:

```bash
git checkout main
git merge plan
git push
```

---

## 5. Cursor čati un rules

| Čats | Rules | Ko dara |
|------|-------|---------|
| **Ilze — plāns** | `plan-only` rule | Tikai `plan/`, DE teksti — ieslēdz čatā vai atver `plan/` failu |
| **Eduards — review** | `review-only` rule | Lasīt `plan/`; `src/` tikai pēc apstiprinājuma |

**Ilze**: čatā pievieno rule `@plan-only` vai atver failu no `plan/`.
**Eduards**: monitorēšanai pietiek ar `AGENTS.md`; kodēšanai `src/` — rule `@review-only`.

---

## 6. Kad sākt `src/` (WP kods)

1. Plāns `plan/` apstiprināts un merge uz `main`
2. Eduards: `git checkout -b dev` no `main`
3. WP custom kods tikai `src/` — nevis visa WP instalācija repozitorijā
4. Pēc izmaiņām: commit `src/`, atjaunināt `docs/HANDOFF.md`

---

## 7. Problēmas

| Problēma | Risinājums |
|----------|------------|
| OneDrive permission | Pārvietot uz `C:\Projects\` vai `~/Projects/` |
| Čats rāda veco info | Skatīt Git / `docs/HANDOFF.md` |
| Konflikts `plan/` | `git pull` pirms commit; risināt konfliktus failā |
| CRLF vs LF | `.gitattributes` jau iestatīts uz LF |
