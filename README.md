# Dämmstoffe Weidenhof — Design-Vorschau

Statische Website als **Stilvorschau**: Sie zeigt, in welchem Look-and-Feel eine Seite
gebaut werden kann. Layout, Komponenten und Interaktionen sind 1:1 nach einer bestehenden
Vorlage aufgebaut; sämtliche Unternehmensinhalte sind frei erfunden.

> **Alles Inhaltliche ist Beispielmaterial.** „Dämmstoffe Weidenhof“ existiert nicht.
> Firmenname, Logo, Anschrift, Telefonnummer, E-Mail-Adresse, Öffnungszeiten, Produkte,
> Preise und Kundenstimmen sind erfunden. Der Hinweis steht auch sichtbar im
> [Impressum](impressum.html).

## Seiten

| Datei | Inhalt |
| --- | --- |
| `index.html` | Startseite: Hero-Slider, Sortiment, Bild-Text-Strecke, Konfigurator-Teaser, Energie-Abschnitt, Bewertungen, Galerie, Kontakt |
| `konfigurator.html` | Vierstufiger Berater: Bereich → Fläche → Anspruch → Empfehlung |
| `sortiment.html` | Produktübersicht mit Kategoriefilter und Live-Suche |
| `impressum.html` | Impressum und Datenschutzhinweise (Platzhalter) |

## Aufbau

```
index.html  konfigurator.html  sortiment.html  impressum.html
css/style.css            Design-System (Tokens, Komponenten, Dark-Luxury-Skin)
js/main.js               Header, Scroll-Reveal, Slider, Merkliste, Formular, Preloader
js/konfigurator.js       Empfehlungslogik des Konfigurators
js/sortiment.js          Filter und Suche im Sortiment
assets/img/              Logo, Bildmotive, Energie-Grafik, Karte, Partnerlogos
assets/img/zones/        Icons für Wand, Dach, Boden, Keller
```

Keine Build-Tools, kein Framework, keine Abhängigkeiten. Extern geladen wird nur die
Schrift *Jost* von Google Fonts; alle Bilder sind selbst erstellte SVGs und liegen lokal.

## Lokal ansehen

```bash
python3 -m http.server 8000
# danach http://localhost:8000 öffnen
```

Ein Doppelklick auf `index.html` funktioniert ebenfalls, allerdings ist `localStorage`
je nach Browser über `file://` eingeschränkt — dann fehlt die Merkliste.

## Verhalten ohne Backend

Die Seite ist rein statisch:

- **Kontaktformular** prüft die Pflichtfelder und öffnet anschließend das lokale
  E-Mail-Programm (`mailto:`). Es werden keine Daten an einen Server gesendet.
- **Merkliste** liegt ausschließlich im `localStorage` des Browsers (Schlüssel `wh-inquiry`)
  und wird im Kontaktformular zusammengefasst.
- **Konfigurator** rechnet im Browser mit Richtwerten aus `js/konfigurator.js`
  (Materialpreis je m², empfohlene Stärke, 10 % Verschnitt).

## Inhalte austauschen

Für eine echte Seite reicht es, an diesen Stellen zu ersetzen:

1. **Name und Logo** — `assets/img/logo.svg` sowie die Textstellen „Dämmstoffe Weidenhof“.
   Das Logo wird per CSS (`filter: brightness(0) invert(1)`) immer weiß dargestellt,
   die Farbe in der Datei ist also unerheblich.
2. **Kontaktdaten** — Anschrift, Telefon, E-Mail und Öffnungszeiten in allen vier HTML-Dateien.
3. **Bilder** — die SVGs in `assets/img/` durch Fotos ersetzen (gleiche Dateinamen oder
   die `src`- bzw. `--photo`-Angaben anpassen). Die Zonen-Icons brauchen eine helle
   Strichfarbe, weil `[data-theme="dark"] .zone-ico` sie nur aufhellt.
4. **Karte** — `assets/img/map.svg` gegen einen echten Karteneinbindung tauschen;
   der Container `.map-embed` ist bereits auf ein überlagertes `iframe` vorbereitet.
5. **Produkte und Preise** — `sortiment.html` und das Objekt `RECS` in `js/konfigurator.js`.
6. **Impressum** — Pflichtangaben ergänzen und rechtlich prüfen lassen.
