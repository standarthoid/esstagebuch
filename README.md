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
