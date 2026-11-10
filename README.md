# stock-photo-metadata

Claude-Code-Skill, der Stockfotos für **Adobe Stock** und **Shutterstock** vorbereitet.

## Was der Skill kann

- **Metadaten pro Bild** auf Englisch: Titel, Beschreibung, Kategorie und Keywords, passend zu den Limits der beiden Plattformen.
- **Releases prüfen:** Hinweise auf erkennbare Personen, Marken/Logos, Privatgebäude oder -grundstücke, Kunstwerke und KI-Anteile.
- **CSV-Dateien für den Bulk-Upload** bei mehreren Bildern:
  - `adobe-stock-upload.csv` (Spalten `Filename,Title,Keywords,Category,Releases`)
  - `shutterstock-metadaten.csv` (Spalten `Filename,Description,Keywords,Categories,Editorial,Mature content,illustration`)
- **Bilder vorsortieren:** Ordner prüfen und Bilder in `angenommen/` und `abgelehnt/` verschieben, mit einer Begründung pro Bild. Dateien werden verschoben, nicht überschrieben.
- Die Erklärungen an den Nutzer sind Deutsch, die Metadaten Englisch.

## Dateien

| Datei | Inhalt |
|---|---|
| `SKILL.md` | Ablauf, Regeln, Ausgabeformat, CSV-Vorgaben und Sortierlogik |
| `platform-rules.md` | Plattformwerte: Zeichenlimits, Keyword-Anzahl, Kategorielisten, CSV-Formate, abgelehnte Keywords |

## Installation

Den Ordner in das Skill-Verzeichnis von Claude Code kopieren:

```bash
git clone https://github.com/F2-Beamer/stock-photo-metadata.git ~/.claude/skills/stock-photo-metadata
```

Unter Windows (Git Bash) entspricht `~` dem Ordner `C:\Users\<Name>`.

Danach erkennt Claude Code den Skill automatisch, wenn es um Stockfotos, Titel, Beschreibungen, Kategorien, Keywords oder CSV-Uploads geht. Aufruf auch direkt mit `/stock-photo-metadata`.

## Stand und offene Punkte

- Die CSV-Formate beider Plattformen sind durch erfolgreiche Uploads bestätigt.
- Nicht verifiziert: Shutterstock-Beschreibungslimit (200 Zeichen angenommen), Shutterstock-Keyword-Limit (50 angenommen) und die Adobe-Kategorienummern (Stand Trainingswissen).
- Abgelehnte Shutterstock-Keywords sind noch nicht gesammelt. Sie werden in `platform-rules.md` ergänzt, sobald sie bekannt sind.

## Hinweis

Der Skill liefert Vorschläge. Releases und Rechte prüft am Ende der Nutzer selbst. Bei Zweifel gilt ein Bild als nicht einreichbar.

## Lizenz

Noch nicht festgelegt.
