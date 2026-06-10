# Blue ⚡ Website

Professionelle mehrseitige Website für deinen Community Server / Discord Bot **Blue ⚡**.

## Enthalten

- `testtestindex.html` — Startseite mit Hero, Features, Stats, CTA und Animationen
- `testteststatus.html` — Bot Status Seite mit Komponenten, Incidents und Live-Stats
- `testtestimpressum.html` — Impressum-Vorlage
- `testtesttos.html` — Terms of Service Vorlage
- `testtestprivacy.html` — Privacy Policy Vorlage
- `testtestsupport.html` — Weiterleitung zu `https://dsc.blue-lol.de`
- `assets/testteststyles.css` — komplettes modernes Design
- `assets/testtestapp.js` — Animationen, Mobile Menü, Status-/Stats-Ladefunktion
- `data/testteststats.json` und `data/testteststatus.json` — statische Fallback-Daten
- `backend-example/` — optionales Node.js Beispiel für echte Live-Daten

## Wichtige Anpassungen vor dem Upload

1. In `testtestindex.html` die Bot Invite URL ersetzen:

```html
https://discord.com/oauth2/authorize?client_id=DEINE_CLIENT_ID&permissions=8&scope=bot%20applications.commands
```

Ersetze `DEINE_CLIENT_ID` durch die Client-ID deines Discord Bots.

2. In `testtestimpressum.html`, `testtestprivacy.html` und ggf. `testtesttos.html` alle Platzhalter ersetzen:

```txt
[Dein Name / Unternehmen]
[deine E-Mail]
[Straße und Hausnummer]
[PLZ Ort]
```

3. Support-Link ist bereits korrigiert auf:

```txt
https://dsc.blue-lol.de
```

## Live User / Server Stats

Eine reine statische Website kann die echten Discord-Zahlen nicht sicher direkt abrufen, weil der Bot Token niemals im Frontend stehen darf. Deshalb lädt die Website zuerst:

```txt
/api/stats
/api/status
```

Wenn diese Endpunkte nicht existieren, nutzt sie automatisch:

```txt
data/testteststats.json
data/testteststatus.json
```

Du kannst also sofort hosten und später eine API dazuschalten.

## Optional: Backend starten

```bash
cd backend-example
npm install
cp test.env.example .env
# .env öffnen und DISCORD_TOKEN eintragen
npm start
```

Danach ist die Website lokal unter `http://localhost:3000` erreichbar.

Wichtig: Für echte Online-User-Zahlen brauchst du im Discord Developer Portal die passenden Privileged Intents, besonders Presence Intent. Je nach Cache/Shard-Setup können Online-Zahlen trotzdem nur näherungsweise sein.

## Hosting

Für statisches Hosting kannst du den kompletten Ordner ohne `backend-example` auf deinen Webspace hochladen. Für Live-Stats brauchst du zusätzlich einen Node.js Host, VPS, Pterodactyl, Render, Railway oder ähnliches.

## Copyright Footer

Der Footer enthält bereits:

```txt
© 2026 Alle Rechte vorbehalten
```
