# Pizzeria_Da_Luigi_KKW5


## Folie 1

Pizzeria Da Luigi

Überarbeitete Artefakte und Antwortkarten
Business Intelligence HS 2026 · GK Woche 5 · Team Lara, Darren, Daniele, Michele


## Folie 2

System Charter: was wir angepasst haben

Lieferzusage ergänzt

45 Minuten ab Bestellung, davon ca. 10 Min. Lieferweg: Die Küche hat etwa 35 Minuten.

Entscheidungsrollen geklärt (3a)

Bestellannahme und Teigmenge: Küchenchef (Cousin B). Einsatzplan: die Freunde. Preise, Aktionen: Geschäftsführer (Cousin A).

Stakeholder mit Rollen

Geschäftsführer und Küchenchef getrennt aufgeführt, Service und Aushilfen zusammen.

Version V2

Datum 15.10.2026 statt 17.09.2026 (v0).

▸ System Charter öffnen

2


## Folie 3

Causal Loop Diagram

▸ CLD in Vensim öffnen

3


## Folie 4

Kontextdiagramm v8

4


## Folie 5

Drei Antwortkarten

1 · Bestellannahme

Feedback

Entscheidungsperson
Küchenchef (Cousin B)
Entscheidung
Ab wann werden neue Bestellungen abgelehnt?
Schlüsselfrage
Wird eine jetzt angenommene Bestellung innerhalb der Lieferzusage fertig?
Benötigte Antwort
Erwartete Durchlaufzeit in Min., laufend während des Service
Bezug zum Zielmodell
Bestand «Offene Bestellungen», Loop B1 Bestellstopp

2 · Wochenend-Einsatzplan

Feedforward

Entscheidungsperson
Freunde (Service)
Entscheidung
Bis Mittwoch festlegen, wie viele Aushilfen am Fr/Sa eingeplant werden
Schlüsselfrage
Übersteigt die erwartete Spitzennachfrage (18–21 Uhr) die Kapazität des geplanten Personals?
Benötigte Antwort
Prognose Bestellungen pro Stunde für Fr und Sa aus 5 Quellen, mit Spanne tief/hoch, wöchentlich bis Mittwoch
Bezug zum Zielmodell
Erwartete Nachfrage Prognose, Personal im Einsatz, Störgrössen S1–S4

3 · Teigmenge

Feedforward

Entscheidungsperson
Küchenchef (Cousin B)
Entscheidung
Wie viel Teig wird vor dem Service vorbereitet?
Schlüsselfrage
Reicht der Teig für die erwartete Nachfrage, ohne viel Rest?
Benötigte Antwort
Prognose Pizzen pro Tag, am Vortag
Bezug zum Zielmodell
Vorbereitete Teigmenge, Störgrössen S1, S3

5


## Folie 6

Karte 2: Prognose aus fünf Quellen statt Bauchgefühl

1 · Basis
Ø Bestellungen pro Stunde am gleichen Wochentag, letzte 4 Wochen (Kassensystem)

2 · Wetter (S1)
Regen am Abend: Zuschlag, z. B. +20 %

3 · Kalender und Anlässe (S1)
Fest im Quartier, Fussballspiel, Feiertag, Schulferien

4 · Gruppenreservationen (S2)
Fix gebuchte Bestellungen aus dem Reservationsbuch

5 · Plattform-Aktionen (S3)
Angekündigte Rabattaktion der Liefer-App: Zuschlag

Prognose
Bestellungen/Std. Fr und Sa 18–21 Uhr, tief und hoch

Actionable Signal
Wenn die Prognose (hoch) über 24 Bestellungen/Std. liegt, dann bis Mittwoch eine Aushilfe zusätzlich einplanen; über 36 zwei.

24 = Kapazität von 2 Personen × 12 Bestellungen/Std.

Formel: Prognose = Basis × Wetterfaktor × Anlassfaktor + Reservationen + Aktionszuschlag. Die Faktoren sind Annahmen und werden mit den Kassendaten kalibriert. Jeden Montag Prognose und tatsächliche Bestellungen vergleichen, um den Fehler zu messen.

6

> Notizen: Bisher stand auf Karte 2 nur «Prognose Bestellungen pro Abend». Neu kombinieren wir fünf Quellen: die Kassendaten als Basis und die Störgrössen S1 bis S3 als Zu- oder Abschläge. Ausfälle von Aushilfen (S4) betreffen nicht die Nachfrage, sondern die Kapazität: Wer absagt, wird im Einsatzplan ersetzt. Lücke: Wetter und Anlässe sind heute nicht mit den Kassendaten verknüpft, Plattform-Bestellungen fehlen im Kassensystem (F13), der Einsatzplan läuft über WhatsApp.


## Folie 7

Wichtigste Karte: Bestellannahme als Kette

Karte 1 ist die wichtigste: Sie ist die Entscheidung im Fokus des Kontextdiagramms, NGT-Rang 1 und führt heute nach Bauchgefühl zu verspäteten Lieferungen.

Data

Kassensystem: Bestellungen mit Zeit und Kanal; neu: Zeitpunkt «fertig»

Insight

In der Spitze wächst die Schlange, weil 2 Personen nur 24 von 28 Bestellungen/Std. schaffen

Signal

Wenn Durchlaufzeit > 22.5 Min., dann beginnt die Ablehnung; ab 37.5 Min. alles (Feedback)

Decision

Neue Bestellungen teilweise oder ganz ablehnen

Action

Küchenchef pausiert die Plattform, Service nennt längere Wartezeit

System Response

Schlange und Durchlaufzeit sinken, B1 gleicht aus; verlorene Bestellungen steigen

Consequences

+ Zusage gehalten, weniger Fehler · − Umsatz verloren, Abwanderung

Actionability Analysis

Impact Analysis

Erkenntnis: Der Bestellstopp behandelt das Symptom. Die Ursache, zu wenig Personal in der Spitze, löst Karte 2 mit Feedforward.

7
