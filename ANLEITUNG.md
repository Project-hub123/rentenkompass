# RentenKompass als installierbare App (PWA)

## Inhalt
- `index.html` – die App (Rechenkern, Oberfläche)
- `manifest.webmanifest` – Name, Icon und Farben der App
- `sw.js` – Service Worker (App läuft nach dem ersten Laden auch offline)
- `icons/` – App-Symbole

## Wichtig
Eine PWA funktioniert nur, wenn sie über eine **https-Adresse** geladen wird.
Per Doppelklick vom USB-Stick (file://) läuft die App weiterhin normal, lässt sich aber nicht installieren.

## Variante A: GitHub Pages (kostenlos, bleibt dauerhaft online)
1. Konto auf github.com anlegen und ein neues, öffentliches Repository erstellen (z. B. `rentenkompass`).
2. Alle Dateien dieses Ordners hochladen (inkl. Ordner `icons`; "Add file" > "Upload files").
3. Im Repository: Settings > Pages > Quelle "Deploy from a branch", Branch `main`, Ordner `/ (root)` > Save.
4. Nach ein bis zwei Minuten ist die App erreichbar unter `https://DEINNAME.github.io/rentenkompass/`.

## Variante B: Netlify Drop (am schnellsten)
1. netlify.com/drop öffnen.
2. Den ganzen Ordner `rentenkompass-pwa` ins Fenster ziehen.
3. Du erhältst sofort eine https-Adresse. Wer ein Konto anlegt, behält die Seite dauerhaft.

## Auf dem Handy installieren
- Adresse im Browser öffnen.
- Samsung Internet: Menü (drei Striche) > "Seite hinzufügen zu" > "Startbildschirm".
- Chrome (Android): Menü (drei Punkte) > "App installieren" bzw. "Zum Startbildschirm hinzufügen".
- Die Menünamen können je nach Version leicht abweichen.

## Neue QR-Code-Adresse
Die neue Adresse (github.io oder netlify.app) ersetzt den bisherigen Link. Dafür einen neuen QR-Code erzeugen.

## Wenn du die App änderst
In `sw.js` die Zeile `const CACHE = "rk-v2";` auf `rk-v3` (usw.) erhöhen, sonst zeigen Handys weiter die alte Version.

## Datenschutz
Alle Eingaben bleiben im Browser des Geräts (localStorage). Es gibt keinen Server und keine Übertragung.

## Neu in Version 5
- Hilfe-Fenster (Button "?") mit den häufigsten Fragen.
- Darstellung Auto / Hell / Dunkel (Button in der Kopfzeile).
- "Daten sichern": Sicherungscode erstellen und auf einem anderen Gerät einfügen. Eine Anmeldung gibt es bewusst nicht, alle Daten bleiben auf dem Gerät.

## Ohne Anmeldung für alle, die den QR-Code scannen
Die App muss auf einer eigenen https-Adresse liegen (Netlify oder GitHub Pages, siehe oben). Dort ist sie ohne Konto bei irgendeinem Anbieter öffnbar.
