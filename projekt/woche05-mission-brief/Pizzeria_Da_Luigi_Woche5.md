# Pizzeria_Da_Luigi_Woche5


## Folie 1

Pizzeria Da Luigi

Überarbeitete Artefakte und Actionable Signals
Business Intelligence HS 2026 · GK Woche 5 · Team Lara, Darren, Daniele, Michele · 15.10.2026

> Notizen: Wir zeigen, was wir an System Charter, CLD, Stock-Flow und Kontextdiagramm verbessert haben, und wie daraus unsere Antwortkarten und das Actionable Signal entstanden sind.


## Folie 2

Ein roter Faden: von der Charter bis zum Signal

1

System Charter V2

Rollen, Lieferzusage 45 Min.

2

CLD

Loops und Verzögerungen

3

Stock-Flow v8

Fehler behoben, Feedforward-Schalter

4

Kontextdiagramm v8

Störgrössen S1–S6 verbunden

5

Antwortkarten

3 Entscheidungen, 1 Signal

Unsere Kernaussage
Der Bestellstopp (Feedback) reagiert erst, wenn sich der Stau schon gebildet hat. Wer das Wochenende vorab nach Prognose plant (Feedforward), verhindert den Stau: In der Simulation gehen dann keine Bestellungen mehr verloren.

2

> Notizen: Jedes Artefakt übernimmt Namen und Zahlen aus dem vorherigen. Deshalb haben wir in genau dieser Reihenfolge überarbeitet.


## Folie 3

System Charter V2: Rollen und Zahlen geklärt

Wer entscheidet (3a)

Bestellannahme bei hoher Auslastung und Teigmenge: Küchenchef (Cousin B). Einsatzplan: die Freunde. Preise und Aktionen: Geschäftsführer (Cousin A).

Lieferzusage

45 Minuten ab Bestellung, davon ca. 10 Minuten Lieferweg. Daraus leitet sich die Schwelle im Stock-Flow ab.

Was die Charter gemeinsam mit den Antwortkarten liefert

Die drei wiederkehrenden Entscheidungen (Abschnitt 4) sind genau unsere drei Antwortkarten: Teigmenge, Wochenend-Einsatzplan und Bestellannahme. Heute entscheiden alle drei nach Erfahrung oder Bauchgefühl.

35
Minuten Küchenbudget pro Lieferbestellung

▸ System Charter öffnen

3


## Folie 4

CLD: fünf Loops erklären den Stau

R1

Stress-Spirale
Auslastung → Fehler → noch mehr Auslastung

B1

Bestellstopp
Auslastung → Ablehnungen → weniger angenommene Bestellungen

B2

Ruf und Nachfrage
Lieferzeit → Bewertung → Online-Nachfrage (verzögert)

B3

Personalplanung
Auslastung → Personal (verzögert, Plan wöchentlich)

R2

Teigvorrat
Bestellungen → Teigmenge → weniger Ausverkauf

Geschärft: «Online-Nachfrage» statt «Nachfrage», weil nur Online-Kunden die Plattform-Bewertung sehen. Grau = externe Treiber.

▸ CLD in Vensim öffnen

4

> Notizen: R = verstärkend, B = ausgleichend. Kurzfristig greift nur B1, der Bestellstopp. Die anderen ausgleichenden Loops wirken erst nach Tagen oder Wochen.


## Folie 5

Stock-Flow v8: ein Rechenfehler weniger, ein Hebel mehr

Doppelzählung behoben

Durchlaufzeit ohne Stau jetzt 20 statt 25 Min. Vorher wurden auch an ruhigen Abenden 17 % abgelehnt.

Nachfrage aus der Charter

9 Bestellungen/Std., Spitze 28/Std. (18–21 Uhr), 2 Personen in der Küche.

Feedforward-Schalter

Bei Prognose über der Kapazität wird vorab eine Aushilfe eingeplant.

▸ Stock-Flow in Vensim öffnen

5

> Notizen: Bestände: Offene Bestellungen (Schlange), Bestellungen in Zubereitung (Ofen), Verlorene Bestellungen. Die Entscheidungsregel oben: Ab 22.5 Minuten wahrgenommener Durchlaufzeit beginnt der Küchenchef abzulehnen, ab 37.5 Minuten lehnt er alles ab.


## Folie 6

Simulation: Mit Feedforward geht keine Bestellung verloren

≈ 10
verlorene Bestellungen ohne Feedforward (9 %)

0
mit einer Aushilfe mehr, geplant nach Prognose

Vergleich in Vensim: «Feedforward Schalter» 0 und 1. Die Durchlaufzeit bleibt mit Feedforward bei 20 Min., ohne steigt sie in der Spitze auf ca. 25 Min.

6

> Notizen: Von 111 Bestellungen am Freitagabend gehen ohne Vorsteuerung rund 10 verloren, weil 2 Personen nur 24 Bestellungen pro Stunde schaffen, die Spitze aber 28 bringt. Mit Feedforward sind es 0.


## Folie 7

Kontextdiagramm v8: Störgrössen verbunden

S1–S3 → Prognose

Wetter, Anlässe, Reservationen und Plattform-Aktionen sind vorab bekannt: Basis für Feedforward.

Abwanderung (B4)

Abgewiesene Kundschaft wechselt zur Konkurrenz.

Datenlücken

Plattform-Bestellungen und Zeitpunkt «fertig» fehlen.

▸ Kontextdiagramm öffnen

7


## Folie 8

Feedback reagiert auf den Stau, Feedforward verhindert ihn

Feedback

Bestellstopp (B1)

Misst die Abweichung im laufenden Betrieb: Die Durchlaufzeit ist zu hoch, also werden neue Bestellungen abgelehnt.

Beispiel: Freitag 19:10 Uhr, 6 Bestellungen in der Schlange → Plattform pausieren.

Feedforward

Einsatzplan nach Prognose

Misst Störgrössen, bevor sie wirken: Regen, Anlass oder Reservation fürs Wochenende sind bis Mittwoch bekannt.

Beispiel: Mittwoch, Regen und 20er-Reservation für Samstag → eine Aushilfe zusätzlich einplanen.

8


## Folie 9

Drei Antwortkarten für drei Entscheidungen

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

2 · Wochenend-Einsatzplan

Feedforward

Entscheidungsperson
Freunde (Service)
Entscheidung
Wie viele Aushilfen werden für Fr/Sa eingeplant?
Schlüsselfrage
Ist die Nachfrage am Wochenende höher als die Kapazität des geplanten Personals?
Benötigte Antwort
Prognose Bestellungen pro Abend, bis Mittwoch

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

Karte 1 ist die wichtigste: Entscheidung im Fokus, NGT-Rang 1, heute Bauchgefühl mit verspäteten Lieferungen.

▸ Antwortkarten öffnen

9


## Folie 10

Von den Daten zur Wirkung: Karte 1 als Kette

Data

Kassensystem: Bestellungen mit Zeit und Kanal; neu: Zeitpunkt «fertig»

Insight

In der Spitze wächst die Schlange, weil 2 Personen nur 24 von 28 Bestellungen/Std. schaffen

Signal

Wenn Durchlaufzeit > 22.5 Min., dann beginnt die Ablehnung; ab 37.5 Min. alles

Decision

Neue Bestellungen teilweise oder ganz ablehnen

Action

Küchenchef pausiert die Plattform, Service nennt längere Wartezeit

System Response

Schlange sinkt, Durchlaufzeit sinkt, B1 gleicht aus; verlorene Bestellungen steigen

Consequences

+ Zusage gehalten, weniger Fehler · − Umsatz verloren, Abwanderung

Actionability Analysis

Impact Analysis

Erkenntnis: Der Bestellstopp behandelt das Symptom. Die Ursache, zu wenig Personal in der Spitze, adressiert Karte 2 mit Feedforward.

10


## Folie 11

Was noch offen ist und wie wir es prüfen

1

Daten erfassen

Zeitpunkt «fertig» und Plattform-Bestellungen ins Kassensystem (F12, F13)

2

Annahmen messen

Leistung pro Person (12/Std.), Ofenplätze (10) und Spitzenlast mit Kassendaten prüfen

3

Kleinster erster Schritt

4 Wochen Strichliste an Fr/Sa: abgelehnte und verspätete Bestellungen zählen, kostet 0 Franken

4

BI Mission Brief

Karte 1 und die Wirkungshypothesen werden Abschnitt 4–6 des Briefs

11


## Folie 12

Alle Dateien zum Öffnen

System Charter V2  ·  System_Charter_A3_Pizzeria_Da_Luigi_V2.docx
CLD (Vensim)  ·  pizzeria_da_luigi_cld_finished.mdl
Stock-Flow v8 (Vensim)  ·  pizzeria_da_luigi_sfd_v8.mdl
Kontextdiagramm v8  ·  Kontextdiagramm_Pizzeria_Da_Luigi_v8.jpg
Antwortkarten  ·  Antwortkarten_Pizzeria_Da_Luigi.docx

Die Links funktionieren, wenn die Präsentation aus dem Ordner «bi abgaben» in PowerPoint (Desktop) geöffnet wird.
