# Plattform-Regeln: Adobe Stock und Shutterstock

Zuletzt aktualisiert: 2026-11-08 (nach erfolgreichen Uploads beider Plattformen)

## Status

- **Adobe Stock CSV:** verifiziert. Upload mit 19 Bildern funktionierte.
- **Shutterstock CSV:** verifiziert. Format aus der Shutterstock-Beispieldatei, Upload funktionierte.
- **Shutterstock Kategorienamen:** in der CSV klein und englisch (siehe Liste unten). Upload mit diesen Namen funktionierte.
- **Nicht verifiziert:** Shutterstock-Beschreibungslimit (200 Zeichen angenommen), Adobe-Kategorienummern (Liste unten, Stand Trainingswissen), Shutterstock-Keyword-Limit (50 angenommen).
- **Abgelehnte Keywords:** noch unbekannt. Siehe Abschnitt unten.

## Adobe Stock

CSV-Upload, Spalten exakt in Englisch: `Filename,Title,Keywords,Category,Releases`. Nur `Filename` ist Pflicht.

- Filename: vollständiger Dateiname mit Endung, z. B. `image.jpg`. Nicht in Anführungszeichen.
- Title: max. 200 Zeichen (verifiziert über Upload-Dialog). Nicht in Anführungszeichen, wenn kein Komma enthalten ist.
- Keywords: durch Kommas getrennt, **max. 49**, nach Relevanz sortiert. In Anführungszeichen.
- Category: numerischer Code (Liste unten). Nicht in Anführungszeichen.
- Releases: Namen der Modell- bzw. Eigentümerfreigaben, genau wie im Adobe-Portal angelegt. Leer lassen, wenn keine vorhanden.
- Trennzeichen: Komma.

Noch nicht verifiziert: Kategorie-Nummern. Das "?"-Symbol im Upload-Dialog verlinkt die offizielle Liste.

### Adobe-Kategorien (Stand Trainingswissen)

1 Animals, 2 Buildings and Architecture, 3 Business, 4 Drinks, 5 The Environment,
6 States of Mind, 7 Food, 8 Graphic Resources, 9 Hobbies and Leisure, 10 Industry,
11 Landscapes, 12 Lifestyle, 13 People, 14 Plants and Flowers, 15 Culture and Religion,
16 Science, 17 Social Issues, 18 Sports, 19 Technology, 20 Transport, 21 Travel

## Shutterstock

CSV-Upload, Trennzeichen Komma, Spalten: `Filename,Description,Keywords,Categories,Editorial,Mature content,illustration`

- Description: Limit ungeprüft, 200 Zeichen angenommen.
- Keywords: Limit ungeprüft, 50 angenommen. In Anführungszeichen.
- Categories: bis zu zwei, komma-getrennt in Anführungszeichen, klein und englisch, z. B. `"nature,parks/outdoor"`.
- Editorial, Mature content, illustration: `no`.
- Keine Release-Spalten im Beispielformat.

### Shutterstock-Kategorien (verwendete Schreibweise in der CSV)

Vom Nutzer bestätigt über Screenshot der Upload-Oberfläche (deutsche Anzeige). Die CSV-Namen sind die englischen Entsprechungen, mit denen der Upload funktionierte:

abstract, animals/wildlife, arts, backgrounds/textures, beauty/fashion, buildings/landmarks,
business/finance, celebrities, education, food and drink, healthcare/medical, holidays,
industrial, interiors, miscellaneous, nature, objects, parks/outdoor, people, religion,
science, signs/symbols, sports/recreation, technology, transportation, vintage

## Abgelehnte Keywords

Shutterstock hat bei einem Upload einige Keywords nicht angenommen. Der Nutzer konnte sie nicht sehen. Sobald bekannt, hier eintragen, mit Datum und Bild. Diese Wörter bei künftigen Uploads nicht verwenden:

- (noch unbekannt)
