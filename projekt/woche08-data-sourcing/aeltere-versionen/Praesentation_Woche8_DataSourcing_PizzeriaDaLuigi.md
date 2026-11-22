# Praesentation_Woche8_DataSourcing_PizzeriaDaLuigi


## Folie 1

Data Sourcing Plan und Provenance Register

Pizzeria Da Luigi · Business Intelligence HS2026 · Abgabe Woche 8

> Notizen: Wir stellen unser Abgabedokument Woche 8 vor. Es baut auf der Data Gap Map aus Woche 7 auf: Für jede Lücke legen wir fest, woher die Daten kommen, wer sie erfasst, was es kostet und wie Herkunft und Datenschutz gesichert sind.


## Folie 2

1 Ausgangslage

Entschieden wird am Donnerstag für Sa und So: Teigmenge, Aushilfen und angezeigte App-Wartezeit. Dafür braucht es vier Informationsanforderungen:

| IR | Informationsanforderung |
| --- | --- |
| IR-01 | Nachfrage pro Tag, Stunde und Kanal (vor Ort, App, Telefon) |
| IR-02 | Teigmenge für Sa und So, 2 Tage im Voraus |
| IR-03 | Ofenkapazität in Pizzen pro Stunde im Vergleich zur Nachfrage |
| IR-04 | Absagen, Verspätungen und Wirkung auf die Kundenzufriedenheit |

Rahmen: Küche Sa und So 11 bis 22 Uhr. App-Bestellungen über Just Eat und Uber Eats, deren Kuriere ausliefern. Telefon nur Abholung. Der Engpass ist der Ofen mit dem Pizzaiolo, deshalb misst IR-03 in Pizzen.

2


## Folie 3

2 Data Sourcing Plan: Quellen und Technik

| ID | Daten | Technik | Quelle | Lücke |
| --- | --- | --- | --- | --- |
| SP-01 | Telefonbestellungen | Primärerhebung, manuell | Kürzel «T» auf dem Bon, Übertrag in die Kasse | G-01 |
| SP-02 | Absagen mit Grund | Primärerhebung und Systemexport | Kürzel auf dem Bon; App-Absagen aus dem Export | G-02 |
| SP-03 | Fertig-Zeit | Instrumentierung | «Fertig»-Taste in der Kasse, ohne Login | G-03 |
| SP-04 | Teigprotokoll | Primärerhebung, Formular | Liste in der Küche | G-04 |
| SP-05 | Bestellungen | Systemexport | Kasse (CSV), Partner-Portale der Plattformen | G-06 |
| SP-06 | Wetter | Open Data, eigene Notiz | MeteoSchweiz; Prognose am Do notieren | G-05 |
| SP-07 | Events | öffentliche Quelle | Veranstaltungskalender der Gemeinde | G-05 |
| SP-08 | Ist-Besetzung | Systemexport | Zeiterfassung | G-07 |
| SP-09 | Abbrüche in der App | Anbieter fragen, sonst Feldexperiment | 2 Wochenenden mit unterschiedlicher Wartezeit | G-09 |
| SP-10 | Bewertungen | manuelle Sichtung | Google, App | G-10 |
| SP-11 | Warum bei Sonne weniger bestellt wird | qualitative Befragung | Kurzfrage in der App, Gespräche mit Stammkunden | G-11 |

3


## Folie 4

2 Data Sourcing Plan: Verantwortung und Akzeptanz

| ID | Daten | Wer | Start | Akzeptanzkriterium |
| --- | --- | --- | --- | --- |
| SP-01 | Telefonbestellungen | Service | sofort | ≥ 95 % in der Kasse, 4 Wochenenden |
| SP-02 | Absagen mit Grund | Service | sofort | Nachfrage = angenommen + abgelehnt berechenbar |
| SP-03 | Fertig-Zeit | Pizzaiolo | sofort | ≥ 90 % der Bestellungen |
| SP-04 | Teigprotokoll | Küchenchef | sofort | 6 Wochenenden lückenlos |
| SP-05 | Bestellungen | Datenverantwortliche | Woche 8 | Duplikate < 1 % |
| SP-06 | Wetter | Schichtleitung | 1. Wochenende | Prognose und Ist für jedes Wochenende |
| SP-07 | Events | Schichtleitung | 1. Wochenende | Spalte pro Tag gefüllt |
| SP-08 | Ist-Besetzung | GF | 1. Wochenende | Besetzung pro Stunde |
| SP-09 | Abbrüche in der App | GF | 3. Wochenende | Abbruchquote je Wartezeit |
| SP-10 | Bewertungen | Schichtleitung | wöchentlich | Datum und Sterne pro Woche |
| SP-11 | Gründe bei Sonne | Service | 3. Wochenende | ≥ 20 Antworten |

4

> Notizen: GF = Geschäftsführer. Teigprotokoll: angesetzte Teiglinge (Do für Sa, Fr für So), übrige (weiterverwendet oder verworfen), Teig ausgegangen ja/nein. Bedarf = angesetzt minus übrig. Die Ofenkapazität (G-08) wird aus SP-03 und SP-08 berechnet.


## Folie 5

3 Zugang, Kosten und Qualität

Die Erfassung kostet vor allem Arbeitszeit: rund 35 Min. pro Wochenende im Betrieb und 30 Min. Aufbereitung am Montag (Schätzung).

| Quelle | Zugang | Qualität | Hauptrisiko | Kosten (Schätzung) |
| --- | --- | --- | --- | --- |
| Kasse | eigenes System, CSV-Export | gut | nur angenommene Bestellungen; Telefon nicht getrennt | ca. 18 Min. pro Wochenende |
| Lieferplattformen | Partner-Portal, Exportumfang prüfen | gut | zwei Plattformen zusammenführen; Doppelzählung | ca. 10 Min. pro Woche |
| Teigprotokoll | eigenes Formular | mittel | Einträge fehlen im Stress | ca. 5 Min. pro Wochenende |
| Zeiterfassung | eigenes System | gut | Pausen ungenau erfasst | keine |
| MeteoSchweiz | Open Data, frei | gut | keine archivierte Prognose | ca. 2 Min. pro Woche |
| Eventkalender | öffentlich | mittel | kleine Events fehlen | ca. 2 Min. pro Woche |
| Bewertungen | öffentlich, kein Export | schwach | wenige, eher negative | ca. 5 Min. pro Woche |
| Befragung | eigene Erhebung | mittel | nur Stammkunden, geschönte Antworten | ca. 15 Min. pro Wochenende |

5


## Folie 6

4 Provenance Register

| ID | Datensatz | Herkunft | Erfasst durch | Speicherort | Aktualisierung | Rechte |
| --- | --- | --- | --- | --- | --- | --- |
| PR-01 | Kassenbestellungen | Kasse | System, Service | /rohdaten/kasse | täglich | intern |
| PR-02 | Plattform-Bestellungen, Absagen | Partner-Portale | System | /rohdaten/app | täglich | Partnervertrag |
| PR-03 | Fertig-Zeiten | Kasse | Pizzaiolo | /rohdaten/kasse | pro Bestellung | intern, ohne Personenbezug |
| PR-04 | Teigprotokoll | Formular Küche | Küchenchef | /rohdaten/teig | Do, Fr, So | intern |
| PR-05 | Wetter (Prognose, Ist) | MeteoSchweiz | Schichtleitung | /rohdaten/wetter | Do und Mo | Open Data, Quelle nennen |
| PR-06 | Events | Kalender Gemeinde | Schichtleitung | /rohdaten/wetter | wöchentlich | öffentlich |
| PR-07 | Ist-Besetzung | Zeiterfassung | System | /rohdaten/personal | nach jedem Wochenende | intern, nur pro Stunde |
| PR-08 | Bewertungen | Google, App | Schichtleitung | /rohdaten/bewertungen | wöchentlich | öffentlich, ohne Namen |
| PR-09 | Befragung | App, Gespräche | Service | /rohdaten/befragung | pro Wochenende | anonym |

6

> Notizen: Weg bis zur Prognose: Export, Kanal zuordnen und Duplikate entfernen, mit Wetter und Events verbinden, pro Stunde aggregieren. Jeder Schritt wird mit Regel, Datum, Version und Verantwortung festgehalten.


## Folie 7

5 Datenschutz- und Ethik-Check

Kasse und Plattformen enthalten Name und Telefonnummer. Sie werden beim Export entfernt, ausgewertet werden nur anonyme Bestelldaten.

| Prüfpunkt | Massnahme |
| --- | --- |
| Kunden | Name und Telefonnummer beim Export löschen; Bewertungen nur mit Datum und Sternen |
| Lieferplattformen | verarbeiten Name und Adresse der Kunden in eigener Verantwortung; die Pizzeria übernimmt nur Bestelldaten ohne Personenbezug |
| Mitarbeitende | Fertig-Taste ohne Login, also keiner Person zuordenbar; Auswertung nur pro Stunde (keine Verhaltensüberwachung nach ArGV 3, Art. 26) |
| Zweck und Zugriff | nur für die Wochenendplanung; Rohdaten nur für GF und Datenverantwortliche |
| Befragung | freiwillig und anonym |
| Bias | abgelehnte Telefonbestellungen und aufgelegte Anrufer bleiben unsichtbar; steht die Pizzeria auf «ausgelastet», entstehen gar keine Bestellungen. Prognose deshalb als Spanne |

7


## Folie 8

6 Erster Datenausschnitt

Der erste Ausschnitt enthält, was heute aus Kasse und Plattformen exportierbar ist, pro Stunde und Kanal.

| Feld | Inhalt | Status |
| --- | --- | --- |
| datum, wochentag, stunde | Zeitpunkt, pro Stunde | vorhanden |
| quelle_kanal | Kasse (vor Ort und Telefon) oder Plattform | Telefon nicht getrennt |
| bestellungen_angenommen, pizzen | Anzahl Bestellungen und Pizzen | vorhanden |
| bestellungen_abgelehnt | Absagen | nur von den Plattformen |
| wetter_ist, temperatur_ist_c | gemessenes Wetter (MeteoSchweiz) | vorhanden |
| wetter_prognose_do | Wetterprognose vom Donnerstag | fehlt |
| event | Event in der Gemeinde | vorhanden |

Die Lücken im Ausschnitt entsprechen der Data Gap Map: Telefon (G-01), Absagen (G-02) und Prognose (G-05) werden mit SP-01, SP-02 und SP-06 geschlossen.

8


## Folie 9

7 Reihenfolge

| Wann | Was | Warum |
| --- | --- | --- |
| Sofort | SP-01 bis SP-04 starten, Export für den Datenausschnitt (SP-05) | grösste Lücken, kleinster Aufwand |
| Ab dem 1. Wochenende | Wetter, Events und Zeiterfassung (SP-06 bis SP-08) | Prognose ist nicht rückwirkend beschaffbar |
| Ab dem 3. Wochenende | Wartezeit-Test (SP-09) und Befragung (SP-11) | braucht normale Wochenenden als Vergleich |
| Nach 4 bis 6 Wochenenden | erste Prognose | weniger Wochenenden sind zu zufällig; bis dahin nur als Spanne |

9


## Folie 10

Fallback

| Falls … | dann … |
| --- | --- |
| die Kasse kein Kürzel «T» kennt | Telefonbestellungen auf einem eigenen Bon-Block |
| eine Plattform keinen Export liefert | App-Absagen wöchentlich aus dem Portal abschreiben |
| die Kasse keine Fertig-Taste hat | Fertig-Zeit von Hand auf dem Bon notieren |
| die Erfassung im Stress lückenhaft ist | Wochenende als unvollständig markieren und nicht für die Prognose nutzen |

Nächster Schritt in Woche 9: Pipeline und Datenmodell mit dem ersten Datenausschnitt.

10
