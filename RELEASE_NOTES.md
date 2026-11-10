## Erste Version: stock-photo-metadata v1.0.0

Claude-Code-Skill für die Vorbereitung von Stockfotos bei **Adobe Stock** und **Shutterstock**.

### Funktionen

- Englische Metadaten pro Bild: Titel, Beschreibung, Kategorie und Keywords
- Hinweise auf mögliche Releases (Personen, Marken/Logos, Privatgebäude, Kunstwerke, KI-Anteile)
- CSV-Dateien für den Bulk-Upload:
  - `adobe-stock-upload.csv`
  - `shutterstock-metadaten.csv`
- Vorsortierung von Bildern in `angenommen/` und `abgelehnt/` mit einer Begründung pro Bild. Dateien werden verschoben, nicht überschrieben.
- Plattformwerte getrennt in `platform-rules.md`, damit sie bei Änderungen an einer Stelle gepflegt werden können

### Stand

- Die CSV-Formate beider Plattformen sind durch erfolgreiche Uploads bestätigt.
- Nicht verifiziert: Shutterstock-Beschreibungslimit (200 Zeichen angenommen), Shutterstock-Keyword-Limit (50 angenommen), Adobe-Kategorienummern (Stand Trainingswissen).
- Abgelehnte Shutterstock-Keywords sind noch nicht gesammelt.
- Bekannte Abweichung: Die Editorial-Ausnahme in `SKILL.md` ist noch nicht entfernt. Bei Bildern mit erkennbarer Anlage ohne Freigabe sollte kein Editorial-Upload vorgeschlagen werden.

### Installation

```bash
git clone https://github.com/F2-Beamer/stock-photo-metadata.git ~/.claude/skills/stock-photo-metadata
```
