# EB Flächenreinigung mit Hochdruck & Schneedienst — Landing Page

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

## Logo

Alle Dateien liegen in `assets/`. Die Schrift ist in Pfade umgewandelt, das Logo sieht also überall gleich aus.

| Datei | Verwendung |
| --- | --- |
| `logo.svg`, `logo.png` | Logo für helle Hintergründe (Briefpapier, Rechnungen, Visitenkarten) |
| `logo-weiss.svg`, `logo-weiss.png` | Logo für blaue/dunkle Hintergründe (Kopfzeile der Seite, Fahrzeug) |
| `logo-icon.svg`, `logo-icon-512.png`, `logo-icon-1024.png` | Nur die Bildmarke (Profilbild für Google, WhatsApp, Instagram) |
| `favicon.svg` | Vereinfachtes Symbol für den Browser-Tab |
| `logo.pdf` | Alle drei Varianten als Vektor-PDF für Druckerei und Folierung |

## Flyer A6

`flyer/flyer-a6-druck.pdf` ist die Druckvorlage für DIN A6 hochkant, 4/4-farbig (Vorder- und Rückseite):

- Endformat 105 × 148 mm, Datenformat 109 × 152 mm (2 mm Beschnitt rundherum)
- Texte mindestens 4 mm vom Rand des Endformats entfernt
- RGB-PDF, Schriften als Vektoren eingebettet, Schatten mit 300 dpi. Die Druckerei wandelt beim Druck in CMYK um
- Der QR-Code führt zu https://emilianbleimn.github.io/EB-Hochdruckreiniger/#anfrage

Quelle ist `flyer/flyer.html`. Nach Änderungen im Browser mit „Drucken → Als PDF speichern“ (Ränder: keine, Hintergrundgrafiken: an) neu erzeugen.
