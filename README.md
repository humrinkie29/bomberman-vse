# 💣 Bomberman VŠE — Escape Game

Webová aplikace pro escape game po budově VŠE Praha (Nová budova).  
Hráči skenují QR kódy, odpovídají na otázky ABCD a postupují stanovišti za čas 60 minut.

---

## 📁 Struktura projektu

```
bomberman-vse/
├── index.html        ← přesměrování (volitelné)
├── game.html         ← stránka pro HRÁČE (QR kódy vedou sem)
├── admin.html        ← tvůj ADMIN panel (správa hry)
├── .gitignore
└── README.md
```

> **Důležité:** Oba soubory jsou čisté HTML — žádný backend, žádný Node.js, žádná instalace.  
> Data se ukládají v `localStorage` prohlížeče. Funguje na libovolném statickém hostingu.

---

## 🚀 Rychlý start — GitHub Pages (doporučeno, zdarma)

### Krok 1 — Vytvoř GitHub účet

1. Jdi na [github.com](https://github.com)
2. Klikni na **Sign up** (vpravo nahoře)
3. Zadej email, heslo, username (např. `sarka-vse`)
4. Potvrď email

---

### Krok 2 — Vytvoř nový repozitář

1. Po přihlášení klikni na zelené tlačítko **New** (vlevo nahoře, nebo na [github.com/new](https://github.com/new))
2. Vyplň formulář:
   - **Repository name:** `bomberman-vse`
   - **Description:** `Escape game VŠE Praha` *(volitelné)*
   - Vyber **Public** *(nutné pro GitHub Pages zdarma)*
   - ✅ Zaškrtni **Add a README file**
3. Klikni na **Create repository**

---

### Krok 3 — Nahraj soubory

#### Možnost A — přes webové rozhraní (nejjednodušší, bez instalace)

1. Jsi na stránce svého repozitáře (vypadá jako `github.com/sarka-vse/bomberman-vse`)
2. Klikni na **Add file** → **Upload files**
3. Přetáhni nebo vyber tyto soubory:
   - `game.html`
   - `admin.html`
   - `README.md` *(přepíše stávající)*
   - `.gitignore`
4. Dole vyplň **Commit changes**: `"Přidání herních souborů"`
5. Klikni na **Commit changes**

#### Možnost B — přes Git (pro pokročilé)

```bash
git clone https://github.com/TVOJE-USERNAME/bomberman-vse.git
cd bomberman-vse
# zkopíruj sem game.html, admin.html
git add .
git commit -m "Přidání herních souborů"
git push origin main
```

---

### Krok 4 — Zapni GitHub Pages

1. V repozitáři klikni na **Settings** (ozubené kolečko, nahoře v menu)
2. V levém menu vyber **Pages**
3. Pod **Source** vyber:
   - Branch: **main**
   - Folder: **/ (root)**
4. Klikni **Save**
5. Počkej ~1 minutu
6. Nahoře se zobrazí zelený banner:  
   **"Your site is published at `https://TVOJE-USERNAME.github.io/bomberman-vse/`"**

> ⚠️ URL bude ve tvém případě vypadat např.:  
> `https://sarka-vse.github.io/bomberman-vse/`

---

### Krok 5 — Nastav URL v admin panelu

1. Otevři `https://TVOJE-USERNAME.github.io/bomberman-vse/admin.html`
2. Přihlaš se heslem `admin123` (změň si ho v Nastavení!)
3. Jdi do sekce **🔲 QR kódy**
4. Do pole **Base URL** zadej:
   ```
   https://TVOJE-USERNAME.github.io/bomberman-vse/
   ```
5. QR kódy se automaticky vygenerují ✅

---

### Krok 6 — Vytiskni QR kódy

1. V admin panelu → **🔲 QR kódy**
2. U každého stanoviště klikni pravým tlačítkem na QR obrázek → **Uložit obrázek**
3. Vytiskni a nalep na stanoviště v budově

Nebo použij URL adresy ručně:
```
Stanoviště 1: https://TVOJE-USERNAME.github.io/bomberman-vse/game.html?station=1
Stanoviště 2: https://TVOJE-USERNAME.github.io/bomberman-vse/game.html?station=2
...
Stanoviště 6: https://TVOJE-USERNAME.github.io/bomberman-vse/game.html?station=6
```

---

## 🎛️ Správa hry — Admin panel

**URL:** `https://TVOJE-USERNAME.github.io/bomberman-vse/admin.html`  
**Heslo:** `admin123` (změň v Nastavení!)

### Co kde nastavíš

| Sekce | Popis |
|---|---|
| 📊 **Dashboard** | Živý přehled týmů, zbývající čas, postup |
| 📍 **Stanoviště** | Editor 6 stanovišť — název, popis, baterie otázek ABCD, nápověda |
| 👥 **Týmy** | Tabulka všech týmů s emailem, časem a postupem |
| 🔲 **QR kódy** | Generování QR kódů k tisku pro každé stanoviště |
| 📧 **Úvodní email** | Text, který hráči uvidí po zadání @vse.cz emailu |
| 🎬 **Úvodní video** | URL YouTube/Vimeo/MP4 videa před startem hry |
| 🎨 **Styl otázek** | Velikost písma, tučnost, barva textu otázek |
| ⚙️ **Nastavení** | Délka hry, počet otázek na stanoviště, max. pokusy |

### Jak upravit otázky

1. Admin → **📍 Stanoviště** → klikni **✏ Upravit** u libovolného stanoviště
2. Scrolluj dolů na sekci **Baterie otázek**
3. Každá otázka má:
   - Text otázky
   - Možnosti A, B, C, D (přidáš/odebeš dle potřeby)
   - Výběr správné odpovědi (zaškrtávací tlačítko ✓)
4. Tlačítko **+ Přidat otázku** přidá další do baterie
5. Klikni **Uložit stanoviště**

> Systém automaticky náhodně vybere N otázek z baterie pro každý tým zvlášť — týmy si nemohou radit!

### Jak přidat úvodní video

1. Admin → **🎬 Úvodní video**
2. Vlož URL:
   - YouTube: `https://www.youtube.com/watch?v=XXXXX`
   - Vimeo: `https://vimeo.com/XXXXX`
   - Přímý MP4: `https://tvoje-url.com/video.mp4`
3. Klikni **Načíst náhled** pro ověření
4. Klikni **Uložit**

---

## 🎮 Flow hráče krok za krokem

```
1. Hráč naskenuje QR kód na stanovišti 1
        ↓
2. Otevře se game.html?station=1
        ↓
3. Zadá @vse.cz email + název týmu
        ↓
4. Zobrazí se "úvodní email" s instrukcemi
   (hráč zaškrtne "přečetl/a jsem")
        ↓
5. Zobrazí se úvodní video
        ↓
6. Klikne "SPUSTIT HRU" → spustí se odpočet 60 minut
        ↓
7. Zodpoví 3 náhodné otázky ABCD ze stanoviště 1
        ↓
8. Zobrazí se nápověda: "Další QR najdeš na..."
        ↓
9. Jde na stanoviště 2, skenuje QR kód
   (game.html?station=2 — timer stále běží!)
        ↓
10. Opakuje pro všechna stanoviště
        ↓
11. Po stanovišti 6: "Gratulujeme! Nahlaste čas."
```

---

## ⚠️ Důležité poznámky

### Data a localStorage

- Všechna data (týmy, postup, nastavení) se ukládají v `localStorage` **prohlížeče zařízení, kde je admin otevřen**
- Hráčská data se ukládají v `localStorage` **jejich telefonu/počítače**
- Pokud hráč zavře prohlížeč a vrátí se zpět na stejné URL, session se automaticky obnoví (dokud nepromazal cookies)
- Data mezi zařízeními se NESDÍLEJÍ — admin a hráči mají každý svůj localStorage

### Doporučení pro den hry

- Otevři admin panel na svém notebooku/tabletu na začátku a nechej ho otevřený
- Nastavení (otázky, email, video) uprav den před hrou — pak jen sleduj dashboard
- Před hrou v adminu klikni **🗑 Reset týmů** pro čistý start
- QR kódy vytiskni A5 nebo A4, zalaminuj pro větší odolnost

### Heslo adminu

Výchozí heslo je `admin123`. **Změň ho před nasazením:**
1. Admin → ⚙️ Nastavení
2. Vyplň **Admin heslo** → Uložit

---

## 🔧 Alternativní hosting (bez GitHubu)

### Netlify (drag & drop, 30 sekund)

1. Jdi na [netlify.com](https://netlify.com) → Sign up (zdarma)
2. Na dashboardu přetáhni **složku `bomberman-vse`** do středu stránky
3. Netlify ji automaticky nasadí
4. Dostaneš URL jako `https://amazing-name-123.netlify.app/`
5. Nastav Base URL v adminu na tuto adresu

### Vercel

1. Jdi na [vercel.com](https://vercel.com) → Sign up
2. **New Project** → **Import** nebo drag & drop
3. Deploy → URL ve stylu `https://bomberman-vse.vercel.app/`

---

## 📱 Testování před hrou

Doporučená kontrola den před hrou:

- [ ] Otevři `admin.html` → přihlaš se
- [ ] Zkontroluj/uprav otázky na všech 6 stanovištích
- [ ] Vlož text úvodního emailu
- [ ] Vlož URL videa a ověř náhled
- [ ] Nastav styl otázek dle potřeby
- [ ] Klikni Reset týmů
- [ ] Otevři `game.html?station=1` v telefonu a projdi celý flow
- [ ] Ověř, že QR kódy vedou na správné URL
- [ ] Vytiskni QR kódy

---

## 🛠️ Budoucí rozšíření (Firebase)

Chceš-li sdílená data přes více zařízení (admin vidí hráče v reálném čase z jiného zařízení), je potřeba přejít na **Firebase Realtime Database** — bezplatný plán pokryje celou hru. Jde o ~30 minut práce — stačí říct a připravím upgrade.

---

*Vytvořeno pro VŠE Praha · Nová budova · Escape Game 2025*
