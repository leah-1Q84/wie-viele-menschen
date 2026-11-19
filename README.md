# Wie viele Menschen?

Ein Rechner für Festivals: Wie viele Besuchende bringen statistisch Beeinträchtigungen, Erkrankungen oder Gewalterfahrungen mit? Gebaut für den Vortrag beim FUTURE OF FESTIVALS 2026, in der saferspaces-CI.

Vorlage ist das Werkzeug „Wie viele Menschen?“ des DigitalService des Bundes (MIT-Lizenz):
https://digitalservice.bund.de/wie-viele-menschen/

## Aufbau

- `index.html`: die komplette Seite, inklusive Styles, Daten und Logik. Keine Build-Schritte, keine Abhängigkeiten.
- `fonts/`: Hausschriften (siehe `fonts/README.md`).
- `.nojekyll`: sorgt dafür, dass GitHub Pages die Dateien unverändert ausliefert.

## Live stellen mit GitHub Pages

1. Neues Repository auf GitHub anlegen, zum Beispiel `wie-viele-menschen`.
2. Diesen Ordner hineinlegen, committen, pushen:

   ```bash
   git init
   git add .
   git commit -m "Wie viele Menschen? Rechner für Festivals"
   git branch -M main
   git remote add origin git@github.com:<dein-account>/wie-viele-menschen.git
   git push -u origin main
   ```

3. Im Repository: Settings → Pages → Build and deployment → Source: „Deploy from a branch“, Branch `main`, Ordner `/ (root)`, speichern.
4. Nach ein bis zwei Minuten ist die Seite unter `https://<dein-account>.github.io/wie-viele-menschen/` erreichbar.

Eigene Domain (zum Beispiel `menschen.saferspaces.io`): in den Pages-Einstellungen unter „Custom domain“ eintragen und beim DNS einen CNAME auf `<dein-account>.github.io` setzen.

## Daten anpassen

Alle Merkmale stehen in `index.html` im Block `GROUPS` (Name, Anteil in Prozent an allen Besuchenden, Quelle, optionale Anmerkung). Die Kacheln oben stehen in `TILES`. Neue Zeile einfügen, speichern, pushen, fertig.

Die Anteile beziehen sich auf die Bevölkerung in Deutschland und werden auf die eingegebene Zahl hochgerechnet. Die drei Zeilen zu Gewalterfahrung rechnen mit 50 % Frauen beziehungsweise Männern unter den Besuchenden.

## Lokal ansehen

Einfach `index.html` im Browser öffnen. Für die Fonts aus `fonts/` braucht es einen kleinen Server, zum Beispiel:

```bash
python3 -m http.server 8000
```

Dann http://localhost:8000 öffnen.
