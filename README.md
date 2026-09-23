# EB Hochdruckreinigung — Landing Page

Einseitige Landing Page in Babyblau/Weiß mit Splash-Design: 3 € pro m², ab 45 m², 150 km Umkreis.
Alles steckt in `index.html` (HTML, CSS und JS), extern geladen wird nur die Schrift *Nunito* von Google Fonts.

Live über GitHub Pages: https://emilianbleimn.github.io/EB-Hochdruckreiniger/

## Anpassen

1. **Empfänger des Formulars:** In `index.html` im `action` des Formulars `DEINE-EMAIL@example.de`
   durch die echte Adresse ersetzen. FormSubmit.co schickt die Anfragen samt Fotos dann per E-Mail
   (beim ersten Absenden kommt eine Bestätigungsmail). Solange der Platzhalter drinsteht, öffnet das
   Formular das E-Mail-Programm (`mailto:info@example.de`).
2. **Impressum:** Platzhalter im Dialog `#dlg` durch die echten Pflichtangaben ersetzen.
3. **Preis, Mindestflächen, Entfernung:** Konstanten `PRICE`, `CALC_MIN`, `NEAR_KM`/`MIN_NEAR`, `MAX_KM`/`MIN_FAR` und `HOME` (Erbach, Odenwald) im Skript am Ende der Datei sowie die Texte im Hero. Die Entfernung wird per PLZ über api.zippopotam.us als Luftlinie berechnet.
4. **Bewertungen:** Array `REVIEWS` im Skript – echte Stimmen eintragen, `beispiel: true` entfernen.
5. **Vorher/Nachher:** die `div.ba__img` durch `<img class="ba__img" …>` mit echten Fotos ersetzen.
