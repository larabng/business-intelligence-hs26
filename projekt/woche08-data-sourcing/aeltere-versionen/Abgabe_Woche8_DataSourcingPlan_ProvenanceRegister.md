Stand: 3. November 2026 · BI HS2026, Abgabe Woche 8

*Rahmen: Die Küche ist Sa und So von 11 bis 22 Uhr offen. App-Bestellungen laufen über Lieferplattformen wie Just Eat (früher eat.ch) oder Uber Eats, deren Kuriere ausliefern. Die Bestelldaten liegen bei der Plattform. Telefonbestellungen gelten als Abholungen.*

# 1 Ausgangslage

Der Plan zeigt, wie die Lücken aus der Data Gap Map geschlossen werden: mit welcher Technik, über welchen Zugang, zu welchen Kosten und ab wann. Entschieden wird am Donnerstag für Samstag und Sonntag: Teigmenge, Aushilfen und angezeigte App-Wartezeit.

| **IR**    | **Informationsanforderung**                                   |
|-----------|---------------------------------------------------------------|
| **IR-01** | Nachfrage pro Tag, Stunde und Kanal (vor Ort, App, Telefon)   |
| **IR-02** | Teigmenge für Sa und So, 2 Tage im Voraus                     |
| **IR-03** | Ofenkapazität in Pizzen pro Stunde im Vergleich zur Nachfrage |
| **IR-04** | Absagen, Verspätungen und Wirkung auf die Kundenzufriedenheit |

*Der Engpass ist der Ofen mit dem Pizzaiolo. Kapazität wird deshalb in Pizzen pro Stunde gemessen. Die Kuriere stellt die Plattform, sie sind kein eigener Engpass. Die Pizza muss aber fertig sein, wenn der Kurier kommt.*

# 2 Data Sourcing Plan

SP-01 bis SP-04 sind neue Erhebungen und starten am nächsten Wochenende. Eine Quelle gilt als geliefert, wenn ihr Akzeptanzkriterium erfüllt ist.

| **ID**    | **Daten**                             | **Technik**                           | **Quelle**                                      | **Lücke** | **Wer**              | **Start**      | **Akzeptanzkriterium**                         |
|-----------|---------------------------------------|---------------------------------------|-------------------------------------------------|-----------|----------------------|----------------|------------------------------------------------|
| **SP-01** | Telefonbestellungen                   | Primärerhebung, manuell               | Kürzel «T» auf dem Bon, Übertrag in die Kasse   | G-01      | Service              | sofort         | ≥ 95 % in der Kasse, 4 Wochenenden             |
| **SP-02** | Absagen mit Grund                     | Primärerhebung und Systemexport       | Kürzel auf dem Bon; App-Absagen aus dem Export  | G-02      | Service              | sofort         | Nachfrage = angenommen + abgelehnt berechenbar |
| **SP-03** | Fertig-Zeit                           | Instrumentierung                      | «Fertig»-Taste in der Kasse, ohne Login         | G-03      | Pizzaiolo            | sofort         | ≥ 90 % der Bestellungen                        |
| **SP-04** | Teigprotokoll                         | Primärerhebung, Formular              | Liste in der Küche                              | G-04      | Küchenchef           | sofort         | 6 Wochenenden lückenlos                        |
| **SP-05** | Bestellungen                          | Systemexport                          | Kasse (CSV), Partner-Portale der Plattformen    | G-06      | Datenverantwortliche | Woche 8        | Duplikate \< 1 %                               |
| **SP-06** | Wetter                                | Open Data, eigene Notiz               | MeteoSchweiz; Prognose am Do notieren           | G-05      | Schichtleitung       | 1\. Wochenende | Prognose und Ist für jedes Wochenende          |
| **SP-07** | Events                                | öffentliche Quelle                    | Veranstaltungskalender der Gemeinde             | G-05      | Schichtleitung       | 1\. Wochenende | Spalte pro Tag gefüllt                         |
| **SP-08** | Ist-Besetzung                         | Systemexport                          | Zeiterfassung                                   | G-07      | GF                   | 1\. Wochenende | Besetzung pro Stunde                           |
| **SP-09** | Abbrüche in der App                   | Anbieter fragen, sonst Feldexperiment | 2 Wochenenden mit unterschiedlicher Wartezeit   | G-09      | GF                   | 3\. Wochenende | Abbruchquote je Wartezeit                      |
| **SP-10** | Bewertungen                           | manuelle Sichtung                     | Google, App                                     | G-10      | Schichtleitung       | wöchentlich    | Datum und Sterne pro Woche                     |
| **SP-11** | Warum bei Sonne weniger bestellt wird | qualitative Befragung                 | Kurzfrage in der App, Gespräche mit Stammkunden | G-11      | Service              | 3\. Wochenende | ≥ 20 Antworten                                 |

*GF = Geschäftsführer. Die Ofenkapazität (G-08) wird aus SP-03 und SP-08 berechnet, nur in Stunden mit Warteschlange.*

*Teigprotokoll (SP-04): angesetzte Teiglinge (Do für Sa, Fr für So), übrige Teiglinge (weiterverwendet oder verworfen) und ob der Teig ausgegangen ist. Bedarf = angesetzt minus übrig. Als Verderb zählen nur die verworfenen.*

# 3 Zugang, Kosten und Qualität

Die Erfassung kostet vor allem Arbeitszeit in den Spitzenstunden. Geschätzt sind das rund 35 Minuten pro Wochenende im Betrieb und 30 Minuten Aufbereitung am Montag.

| **Quelle**                                  | **Zugang**                                             | **Qualität** | **Hauptrisiko**                                                                              | **Kosten (Schätzung)**                                                                                   |
|---------------------------------------------|--------------------------------------------------------|--------------|----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| **Kasse**                                   | eigenes System, CSV-Export                             | gut          | nur angenommene Bestellungen; Telefon nicht getrennt                                         | ca. 5 s pro Bestellung für Kürzel und Fertig-Taste, bei ca. 215 Bestellungen rund 18 Min. pro Wochenende |
| **Lieferplattformen (Just Eat, Uber Eats)** | Bestellberichte im Partner-Portal, Exportumfang prüfen | gut          | Daten liegen bei der Plattform; zwei Plattformen zusammenführen; Doppelzählung mit der Kasse | ca. 10 Min. pro Woche für Export und Zusammenführen                                                      |
| **Teigprotokoll**                           | eigenes Formular                                       | mittel       | Einträge fehlen im Stress                                                                    | ca. 5 Min. pro Wochenende                                                                                |
| **Zeiterfassung**                           | eigenes System                                         | gut          | Pausen ungenau erfasst                                                                       | keine                                                                                                    |
| **MeteoSchweiz**                            | Open Data, frei                                        | gut          | keine archivierte Prognose                                                                   | ca. 2 Min. pro Woche                                                                                     |
| **Eventkalender**                           | öffentlich                                             | mittel       | kleine Events fehlen                                                                         | ca. 2 Min. pro Woche                                                                                     |
| **Bewertungen**                             | öffentlich, kein Export                                | schwach      | wenige, eher negative                                                                        | ca. 5 Min. pro Woche                                                                                     |
| **Befragung**                               | eigene Erhebung                                        | mittel       | nur Stammkunden, geschönte Antworten                                                         | ca. 15 Min. pro Wochenende                                                                               |

# 4 Provenance Register

Das Register zeigt für jeden Datensatz, woher er kommt, wo er liegt und was damit gemacht werden darf.

| **ID**    | **Datensatz**                         | **Herkunft**                    | **Erfasst durch** | **Speicherort**       | **Aktualisierung**    | **Rechte**                          |
|-----------|---------------------------------------|---------------------------------|-------------------|-----------------------|-----------------------|-------------------------------------|
| **PR-01** | Kassenbestellungen (vor Ort, Telefon) | Kasse                           | System, Service   | /rohdaten/kasse       | täglich               | intern                              |
| **PR-02** | App-Bestellungen, App-Absagen         | Partner-Portale der Plattformen | System            | /rohdaten/app         | täglich               | gemäss Partnervertrag der Plattform |
| **PR-03** | Fertig-Zeiten                         | Kasse                           | Pizzaiolo         | /rohdaten/kasse       | pro Bestellung        | intern, ohne Personenbezug          |
| **PR-04** | Teigprotokoll                         | Formular Küche                  | Küchenchef        | /rohdaten/teig        | Do, Fr, So            | intern                              |
| **PR-05** | Wetter                                | MeteoSchweiz                    | Schichtleitung    | /rohdaten/wetter      | Do und Mo             | Open Data, Quelle nennen            |
| **PR-06** | Events                                | Kalender der Gemeinde           | Schichtleitung    | /rohdaten/wetter      | wöchentlich           | öffentlich                          |
| **PR-07** | Ist-Besetzung                         | Zeiterfassung                   | System            | /rohdaten/personal    | nach jedem Wochenende | intern, nur pro Stunde              |
| **PR-08** | Bewertungen                           | Google, App                     | Schichtleitung    | /rohdaten/bewertungen | wöchentlich           | öffentlich, ohne Namen              |
| **PR-09** | Befragung                             | App, Gespräche                  | Service           | /rohdaten/befragung   | pro Wochenende        | anonym                              |

*Weg bis zur Prognose: Export, Kanal zuordnen und Duplikate über die Bestellnummer entfernen, mit Wetter und Events verbinden, pro Stunde aggregieren. Jeder Schritt wird mit Regel, Datum, Version und verantwortlicher Person festgehalten.*

# 5 Datenschutz- und Ethik-Check

Kasse und App enthalten Personendaten wie Name und Telefonnummer. Sie werden beim Export entfernt, die Auswertung nutzt nur anonyme Bestelldaten.

| **Prüfpunkt**         | **Massnahme**                                                                                                                                                                                                                    |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Kunden**            | Name und Telefonnummer beim Export löschen; Bewertungen nur mit Datum und Sternen                                                                                                                                                |
| **Lieferplattformen** | verarbeiten Name und Adresse der Kunden in eigener Verantwortung; die Pizzeria übernimmt nur Bestelldaten ohne Personenbezug                                                                                                     |
| **Mitarbeitende**     | Fertig-Taste ohne Login, also keiner Person zuordenbar; Auswertung nur pro Stunde (keine Verhaltensüberwachung nach ArGV 3, Art. 26)                                                                                             |
| **Zweck und Zugriff** | nur für die Wochenendplanung; Rohdaten nur für GF und Datenverantwortliche                                                                                                                                                       |
| **Befragung**         | freiwillig und anonym                                                                                                                                                                                                            |
| **Bias**              | abgelehnte Telefonbestellungen und aufgelegte Anrufer bleiben unsichtbar, die Nachfrage wird unterschätzt; Prognose deshalb als Spanne. Steht die Pizzeria auf der Plattform auf «ausgelastet», entstehen gar keine Bestellungen |

*Rahmen: Schweizer Datenschutzgesetz (revDSG). MeteoSchweiz wird als Quelle angegeben.*

# 6 Erster Datenausschnitt

Die Pizzeria ist fiktiv, deshalb ist der Ausschnitt simuliert. Er enthält nur, was heute exportierbar ist: Kasse und App für 6 Wochenenden (19.9. bis 25.10.2026), Sa und So, 11 bis 22 Uhr. Datei: Datenausschnitt_Pizzeria_Da_Luigi_SIMULIERT.csv

| **Kennzahl**                                           | **Wert**                                |
|--------------------------------------------------------|-----------------------------------------|
| **Zeilen**                                             | 288 (12 Tage × 12 Stunden × 2 Quellen)  |
| **Bestellungen / Pizzen**                              | 1294 / 2718                             |
| **Spitzenstunde**                                      | 19 Uhr                                  |
| **Stunden nahe an der Kapazität (≥ 41 von 45 Pizzen)** | 20                                      |
| **App-Absagen**                                        | 9                                       |
| **Telefon getrennt erfasst**                           | nein, in der Kasse mit vor Ort zusammen |
| **Absagen vor Ort und Telefon**                        | fehlen                                  |
| **Wetterprognose vom Donnerstag**                      | fehlt, Spalte leer                      |

In der Simulation wurden zusätzlich 38 Telefonbestellungen abgelehnt, die im Export fehlen (Bias aus E-02).

Annahmen der Simulation: Ofenkapazität 45 Pizzen pro Stunde. Bei Regen App +35 %, Telefon +25 %, vor Ort −15 %; bei Sonne vor Ort +10 %, App −10 %. Bei Überlast wird zuerst Telefon, dann App abgelehnt. Events: Dorffest (3.10.) und Fussball-Final (18.10.).

Limitation: Die Wettereffekte sind in die Simulation eingebaut, eine Analyse findet sie deshalb zwangsläufig wieder. Die Daten taugen zum Testen der Pipeline in Woche 9, nicht als Beleg für Zusammenhänge.

# 7 Reihenfolge und Fallback

1.  Sofort: SP-01 bis SP-04 starten und den Export für den Datenausschnitt ziehen (SP-05).

2.  Ab dem 1. Wochenende: Wetter, Events und Zeiterfassung ergänzen (SP-06 bis SP-08).

3.  Ab dem 3. Wochenende: Wartezeit-Test (SP-09) und Befragung (SP-11).

4.  Nach 4 bis 6 Wochenenden: erste Prognose, vorher nur als Spanne.

| **Falls …**                                | **dann …**                                                               |
|--------------------------------------------|--------------------------------------------------------------------------|
| **die Kasse kein Kürzel «T» kennt**        | Telefonbestellungen auf einem eigenen Bon-Block                          |
| **eine Plattform keinen Export liefert**   | App-Absagen wöchentlich aus dem Portal abschreiben                       |
| **die Kasse keine Fertig-Taste hat**       | Fertig-Zeit von Hand auf dem Bon notieren                                |
| **die Erfassung im Stress lückenhaft ist** | Wochenende als unvollständig markieren und nicht für die Prognose nutzen |
