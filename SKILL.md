---
name: stock-photo-metadata
description: Use when preparing photos for upload to Adobe Stock or Shutterstock contributor accounts, when a stock photo needs a title, description, category, or keywords, or when a batch of stock images needs a metadata CSV
---

# Stock-Foto-Metadaten

## Überblick

Erstellt pro Bild englische Metadaten für Adobe Stock und Shutterstock: Titel, Beschreibung, Kategorie und Keywords. Bei mehreren Bildern zusätzlich eine CSV-Datei. Die Erklärungen an den Nutzer bleiben Deutsch, die Metadaten sind Englisch.

Plattformwerte (Zeichenlimits, Keyword-Anzahl, Kategorielisten, CSV-Formate) stehen in `platform-rules.md` im selben Ordner. Lies diese Datei vor jeder Ausgabe. Die CSV-Formate beider Plattformen sind durch erfolgreiche Uploads bestätigt. Offen sind das Shutterstock-Beschreibungslimit und abgelehnte Keywords, siehe `platform-rules.md`.

## Vorgehen

1. **Bild ansehen.** Hauptmotiv, Stimmung, Farben, Ort, Jahreszeit, Tageszeit, sichtbare Personen, Marken, Logos, Gebäude und Privatgelände notieren.
2. **Releases prüfen.** Erkennbare Personen, Marken/Logos, Privatgebäude oder -grundstücke, Kunstwerke, KI-Anteile. Bei einem Treffer den Hinweis in die Ausgabe aufnehmen. Nie behaupten, ein Bild sei frei, wenn Zweifel bestehen.
3. **Titel schreiben.** Konkret, beschreibend, ohne Füllwörter und ohne Markennamen, außer sie sind freigegeben.
4. **Beschreibung schreiben.** Ein bis zwei Sätze, Motiv und Kontext. Innerhalb des Zeichenlimits von Shutterstock bleiben.
5. **Kategorie wählen.** Für Adobe genau eine Nummer und Name aus der Liste. Für Shutterstock bis zu zwei Kategorien aus der Liste in `platform-rules.md`. In der CSV klein und englisch schreiben, z. B. `nature,parks/outdoor`.
6. **Keywords wählen.** Wichtigste zuerst. Motiv, Objekte, Stimmung, Farben, Ort, Jahreszeit, Verwendungszweck. Keine Wiederholungen, keine Begriffe, die nicht zum Bild passen.

## Bilder prüfen und sortieren

Auf Wunsch prüft der Skill alle Bilder eines Ordners und verschiebt sie in die Unterordner `angenommen/` und `abgelehnt/`. Ablauf:

1. Alle JPG/JPEG/PNG direkt im Ordner auflisten (nicht in `angenommen/` oder `abgelehnt/`). Die Unterordner anlegen, falls nicht vorhanden.
2. Jedes Bild ansehen und so bewerten:
   - **Abgelehnt**, wenn eines zutrifft:
     - stark unterbelichtet oder verrauscht, Motiv kaum erkennbar
     - sichtbares Rauschen (Körnung in Himmel, Schatten oder Flächen), auch bei ausreichender Helligkeit
     - geringe Auflösung: unter 4 Megapixel Gesamtpixel (Richtwert, nicht verifiziert)
     - unscharf oder verwackelt
     - sichtbares Logo oder Marke (z. B. Firmenaufdruck auf LKW) ohne Freigabe
     - erkennbare Personen, Privatgebäude, Behörden- oder Militäranlage ohne Freigabe
     - Wasserzeichen, Text im Bild oder starke Artefakte
   - **Angenommen** in allen anderen Fällen.
   - Im Zweifel als "abgelehnt" einordnen und den Grund nennen. Der Nutzer entscheidet.
3. Pro Bild ein Satz Begründung (Deutsch).
4. Dateien verschieben, nicht kopieren. Existiert am Ziel schon eine Datei gleichen Namens, nicht überschreiben, sondern nachfragen.
5. Zusammenfassung: Anzahl angenommen und abgelehnt, Liste der abgelehnten Dateien mit Grund.

Nur angenommene Bilder gehen in die Metadaten-Erstellung und in die CSV-Dateien.

## Ausgabe pro Bild

```
**Dateiname:** <Name>

**Releases:** <Hinweis oder "keine erkennbar">

**Adobe Stock**
- Titel: ...
- Kategorie: <Nr> <Name>
- Keywords: ...

**Shutterstock**
- Beschreibung: ...
- Kategorie 1: ...
- Kategorie 2: ...
- Keywords: ...
```

## CSV bei mehreren Bildern

Zwei Dateien im Ordner der Bilder, UTF-8. Anführungszeichen nur dort, wo ein Feld Kommas enthält (z. B. Keywords). Dateiname, Titel und Kategorie nie in Anführungszeichen. Sonst liest Adobe den Dateinamen mit Anführungszeichen und ordnet die Zeile keinem Bild zu.

**Adobe Stock: `adobe-stock-upload.csv`** (Trennzeichen Komma, Spalten exakt so, Englisch):

`Filename,Title,Keywords,Category,Releases`

- Filename: vollständiger Dateiname mit Endung
- Keywords: Komma-getrennt, max. 49, nach Relevanz
- Category: nur die Nummer, z. B. `11`
- Releases: leer lassen, wenn keine Freigabe vorhanden ist

**Shutterstock: `shutterstock-metadaten.csv`** (Trennzeichen Komma, Format der Shutterstock-Beispieldatei, Upload bestätigt):

`Filename,Description,Keywords,Categories,Editorial,Mature content,illustration`

- Categories: bis zu zwei, komma-getrennt in Anführungszeichen, klein und englisch, z. B. `"nature,parks/outdoor"`
- Editorial, Mature content, illustration: jeweils `no`. Kein Editorial-Upload als Ausweg: Bilder mit erkennbarer Anlage, Gebäude oder Eigentum ohne Freigabe werden abgelehnt (`abgelehnt/`), nicht als Editorial eingereicht.
- Keine Release-Spalten im Format. Releases nur im Hinweis an den Nutzer nennen.

## Regeln

- Keine Halluzinationen: Ort, Tierart, Baumart, Marke nur nennen, wenn sichtbar oder sicher erkennbar. Sonst allgemein formulieren.
- Keine Keywords, die nur Trends oder Suchbegriffe sind, aber nicht zum Bild passen.
- Keine Keyword-Wiederholungen und keine Wörter wie "best", "beautiful", "amazing".
- Zeichenlimits strikt einhalten, nach dem Schreiben zählen.
- Keywords: etwa 30 pro Bild. Shutterstock lehnt einzelne Keywords ab. Der Nutzer meldet sie, sie stehen dann in `platform-rules.md` unter "Abgelehnte Keywords". Solche Begriffe nie wieder verwenden.
- Releases nie verschweigen, auch nicht bei Unsicherheit.

## Häufige Fehler

| Fehler | Korrektur |
|---|---|
| Titel länger als nötig, Keyword-Stuffing | Kurz und konkret, Keywords separat |
| Mehr als eine Kategorie bei Adobe | Genau eine Kategorie |
| Markennamen im Titel | Entfernen oder Release-Hinweis geben |
| Ort geraten | Nur nennen, wenn erkennbar, sonst "lake", "mountain" usw. |
| Plattformlimits aus dem Gedächtnis | Gegen `platform-rules.md` prüfen |
