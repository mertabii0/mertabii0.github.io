# Mertabii — Portfolio (static site)

Dieses Repository enthält die Single-File Portfolio-Website von Mertabii.
Die Seite ist als statische HTML-Datei (`index.html`) aufgebaut und enthält Inline-CSS und Inline-JS für Animationen, Cookie-Consent, Projekt-Modalen und ein individuelles Cursor-Design.

## Inhalt
- `index.html` — Hauptseite (HTML + inline CSS + inline JS)
- `assets/` — Bilder und Favicon (z. B. `instagram.png`, `discord.png`, `github.png`, `favicon.svg`)

## Lokale Vorschau (einfach)
Du kannst die Seite lokal mit einem einfachen HTTP-Server testen. Beispiel (PowerShell / Windows):

```powershell
# mit Python 3
python -m http.server 8000
# oder mit node (falls installiert)
npx http-server -p 8000
```
Dann `http://localhost:8000` im Browser öffnen.

> Hinweis: Dateien direkt per `file://` öffnen kann zu CORS/Resource-Loading-Unterschieden führen; deshalb ist ein lokaler Server empfehlenswert.

## Cookie Consent testen
Die Seite speichert Consent-Status in `localStorage` unter `cookieConsent` und `cookiePreferences`.
Um Tests zu wiederholen, öffne die DevTools Console und führe aus:

```javascript
localStorage.removeItem('cookieConsent');
localStorage.removeItem('cookiePreferences');
location.reload();
```

## Deploy auf GitHub Pages
1. Erstelle ein neues GitHub-Repository (z. B. `mertabii0/portfolio`).
2. Falls noch nicht geschehen, initialisiere git im Ordner und push auf GitHub:

```bash
git init
git add .
git commit -m "Initial commit: portfolio site"
git branch -M main
git remote add origin https://github.com/<dein-username>/<repo>.git
git push -u origin main
```

3. GitHub: Repository → Settings → Pages → Branch: `main`, Folder: `/ (root)` → Speichern.
4. Nach wenigen Minuten ist die Seite erreichbar unter `https://<dein-username>.github.io/<repo>/` (oder wenn du ein User-Site-Repo nutzt `https://<dein-username>.github.io/`).

## Hinweise für Produktion
- Die Seite ist eine einzige Datei (`index.html`) um einfache Deploys zu ermöglichen.
- Wenn du externe Analytics/Tracking einsetzt, lade diese skripte nur, wenn `cookiePreferences.analytics === true`.
- Social images sollten in `assets/` liegen; prüfen, ob die externen URLs korrekt sind.

## Anpassungen & Entwicklung
- CSS und JS sind inline; für größere Erweiterungen empfiehlt sich das Auslagern in `styles.css` / `app.js`.
- Projekte werden durch das `projects`-Objekt im Inline-JS gesteuert (siehe `openModal()`), leicht editierbar.

## Kontakt
- Instagram: https://instagram.com/mertaksoylumusic
- GitHub: https://github.com/mertabii0

---
