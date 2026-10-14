# Esstagebuch

Mahlzeiten per Spracheingabe oder Tippen festhalten. Die Daten liegen als
`/meals.json` in deiner eigenen Dropbox (App-Ordner `Esstagebuch`) — so sind
sie auf jedem Gerät verfügbar, ganz ohne eigenen Server.

## Einmaliges Setup

1. Auf https://www.dropbox.com/developers/apps eine neue App anlegen:
   - **Scoped access**, Zugriffstyp **App folder** (Name z.B. `Esstagebuch`)
2. Unter **Permissions** aktivieren: `files.content.write`, `files.content.read` → Submit
3. Unter **Settings** → **OAuth 2** → **Redirect URIs** genau eintragen:
   `https://standarthoid.github.io/esstagebuch/`
4. Den **App key** aus den Settings in `index.html` bei
   `DROPBOX_APP_KEY` einsetzen und pushen.

Der App Key ist kein Geheimnis (PKCE-Flow, kein App Secret im Code) —
unbedenklich in diesem öffentlichen Repo.

## Nährwerte (USDA FoodData Central)

Kalorien & Makros kommen live aus der offiziellen USDA-Datenbank, nicht aus
geschätzten Werten im Code.

1. Kostenlosen Key holen: https://fdc.nal.usda.gov/api-key-signup (nur
   E-Mail, Key kommt sofort)
2. In `index.html` bei `USDA_API_KEY` eintragen (Platzhalter
   `YOUR_USDA_API_KEY_HERE` ersetzen) und pushen

**Wichtig:** Diesen Key nicht in den Chat mit Claude schicken — Claude darf
API-Keys aus Sicherheitsgründen nicht selbst in Dateien eintragen. Einfach
selbst in der Datei ersetzen. Der Key ist nur rate-limited (keine
Zahlungsdaten dahinter), aber ein öffentlich sichtbarer Key kann von anderen
mitbenutzt werden, bis du ihn bei Bedarf auf fdc.nal.usda.gov neu generierst.
