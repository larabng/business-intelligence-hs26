# Praesentation_final


## Folie 1

Data Sourcing Plan, Provenance Register und erster Datenausschnitt

Priorisierte Lücke G-02: abgelehnte Bestellungen
Pizzeria Da Luigi · Business Intelligence HS 2026 · Abgabe Woche 8, Stand 11. November 2026

G-02

Lücke

SRC

Quellenkandidaten

DATA

Datenausschnitt

> Notizen: Letzte Woche haben wir in der Data Gap Map gezeigt, welche Daten fehlen. Heute zeigen wir für die wichtigste Lücke, G-02, woher die Daten kommen sollen, wie wir die Quellen geprüft haben und was unser erster Datenausschnitt zeigt.


## Folie 2

Abgelehnte Bestellungen sind unsichtbar, deshalb zuerst G-02

Die Kasse erfasst nur angenommene Bestellungen.
Sagt die Küche in der Spitze Nein, entsteht kein Datensatz. Die Nachfrage wird genau dann unterschätzt, wenn am meisten los ist.
Betroffene Entscheide
Mittwoch: Aushilfen für Fr und Sa
Vortag: Teigmenge
Informationsanforderungen
IR-01 Nachfrage pro Tag, Stunde und Kanal
IR-04 Absagen und Verspätungen

Akzeptanzkriterien: Ab wann gilt die Lücke als geschlossen?

AK-1

≥ 95 % der Absagen mit Uhrzeit und Kanal erfasst

AK-2

≥ 90 % der Absagen mit Grund

AK-3

Nachfrage = angenommen + abgelehnt, pro Stunde und Kanal berechenbar

2

> Notizen: Die Kasse zählt nur Bestellungen, die wir annehmen. Wenn wir am Freitagabend um 19 Uhr am Telefon Nein sagen, steht das nirgends. Die Nachfrage wirkt also genau dann zu klein, wenn am meisten los ist. Darauf bauen aber zwei Entscheide auf: am Mittwoch die Aushilfen, am Vortag die Teigmenge. Rechts stehen die drei Akzeptanzkriterien, also ab wann die Lücke als geschlossen gilt.


## Folie 3

Drei Quellenkandidaten, jeder mit eigenem Canvas

SRC-01

Collect

Absage-Erfassung im Lokal

Zugang
Kürzel «A» und Grund auf dem Bon, Strichliste am Telefon
Liefert
Jede Absage vor Ort und am Telefon mit Uhrzeit, Kanal, Pizzen und Grund

geeignet

SRC-02

Share

Export aus den Partner-Portalen

Zugang
Bestellbericht von Just Eat und Uber Eats gemäss Partnervertrag
Liefert
Abgelehnte App-Bestellungen mit Zeitstempel und Status

bedingt geeignet

SRC-03

Build

Anrufprotokoll der Telefonanlage

Zugang
Export der Anrufliste (eingegangen, verpasst)
Liefert
Verpasste Anrufe pro Stunde, nur als Hinweis

nicht geeignet, zurückgestellt

3

> Notizen: Wir haben drei mögliche Quellen geprüft, jede mit einem eigenen Canvas. Erstens: Der Service notiert jede Absage auf dem Bon oder einer Strichliste. Zweitens: Just Eat und Uber Eats liefern die abgelehnten App-Bestellungen als Export. Drittens: Die Telefonanlage zeigt verpasste Anrufe. Das dritte ist nur ein Hinweis, denn ein Anruf ist noch keine Bestellung.


## Folie 4

Muss-Kriterien entscheiden zuerst, dann Qualität und Betrieb

| Kriterium | SRC-01 Erfassung im Lokal | SRC-02 Plattform-Export | SRC-03 Anrufprotokoll |
| --- | --- | --- | --- |
| Stufe 1: Muss-Kriterien |  |  |  |
| Zugang und Nutzung | ja, eigene Daten ohne Personenbezug | ja, mit Auflage: ohne Name und Adresse | Nutzung ungeklärt (Telefonnummern) |
| Plausible Evidenz | ja, direkte Beobachtung | ja, Systemdaten | fraglich, nur Indiz |
| Stufe 2 und 3: Qualität und Betrieb |  |  |  |
| Abdeckung | vor Ort und Telefon | nur App | nur Telefon |
| Messung | von Hand, Grund subjektiv | automatisch, einheitlich | zählt Anrufe, nicht Bestellungen |
| Aufwand | rund 5 s pro Absage | rund 10 Min. pro Woche | Export einrichten, Datenschutz klären |
| Stufe 4: Entscheid |  |  |  |
| Ergebnis | beschaffen | mit Auflage beschaffen | zurückgestellt |

4

> Notizen: Bewertet wird in Stufen. Zuerst kommen die Muss-Kriterien: Dürfen wir auf die Daten zugreifen, dürfen wir sie nutzen, und messen sie überhaupt das Richtige? Die eigene Liste erfüllt alles. Der Plattform-Export geht nur ohne Namen und Adressen. Beim Anrufprotokoll ist die Nutzung ungeklärt, weil Telefonnummern Personendaten sind. Deshalb stellen wir es zurück, egal wie gut es sonst wäre.


## Folie 5

Jede Quelle verzerrt anders, und jede braucht einen Datenschutz-Check

| Prüffrage | SRC-01 Erfassung im Lokal | SRC-02 Plattform-Export | SRC-03 Anrufprotokoll |
| --- | --- | --- | --- |
| Was fehlt systematisch? | Einträge in der hektischsten Viertelstunde; Kunden, die gar nicht fragen | Nachfrage, solange der Modus «ausgelastet» aktiv ist | Wer online bestellt statt anzurufen |
| Richtung der Verzerrung | Unterschätzung | Unterschätzung | Überschätzung (Mehrfachanrufe) |
| Prüfung | Parallelzählung in 2 Spitzenstunden | Protokoll, wann «ausgelastet» aktiv war | Abgleich mit SRC-01 |
| Personenbezug | keiner | Name und Adresse beim Export entfernen | Telefonnummer ist Personendatum |
| Datenschutz-Ergebnis | freigegeben | freigegeben unter Auflagen | ungeklärt |

Ungeprüft ist nicht gleich unverzerrt: Kunden, die gar nicht erst fragen, bleiben in allen Quellen unsichtbar.

5

> Notizen: Keine Quelle ist neutral. Bei der eigenen Liste vergisst man Einträge genau im grössten Stress, also zählen wir zu wenig. Bei der Plattform entsteht im Modus «ausgelastet» gar keine Bestellung, also auch zu wenig. Das Anrufprotokoll zählt zu viel, weil manche dreimal anrufen. Zu jeder Verzerrung haben wir eine Prüfung festgelegt, zum Beispiel eine Parallelzählung in zwei Spitzenstunden.


## Folie 6

Entscheid: SRC-01 und SRC-02 kombiniert, Pilot ab 13. November

Data Sourcing Plan

Gewählter Weg
Kasse (vor Ort, Telefon) über SRC-01, Apps über SRC-02
Zuständig
Service, Geschäftsführer, Datenverantwortliche
Pilot
Fr und Sa, 13./14. und 20./21. November, 17 bis 22 Uhr
Auswertung
23. November gegen AK-1 bis AK-3

Fallback: Was, wenn es nicht klappt?

1

Plattform liefert keinen Export
Absagen wöchentlich von Hand aus dem Portal übertragen

2

Liste im Stress lückenhaft
Wochenende als unvollständig markieren, SRC-03 als Indiz prüfen

3

Beide Quellen reichen nicht
Nachfrage nur als Untergrenze ausweisen, Prognose als Spanne

6

> Notizen: Wir nehmen die eigene Liste und den Plattform-Export zusammen, weil sie verschiedene Kanäle abdecken: Telefon und vor Ort die eine, die Apps die andere. Der Pilot läuft am 13. und 14. sowie am 20. und 21. November, jeweils von 17 bis 22 Uhr. Am 23. November werten wir aus. Und wenn etwas nicht klappt, haben wir einen Plan B: Liefert die Plattform keinen Export, übertragen wir die Absagen von Hand aus dem Portal.


## Folie 7

Der Datenausschnitt ist synthetisch und so gekennzeichnet

52

abgelehnte Bestellungen in DATA-01

4

Abende: Fr und Sa, 23./24. und 30./31. Oktober

2

Dateien aus einem Generatorlauf (DATA-01, DATA-02)

Provenance Register: G-02 → SRC-01, SRC-02 → DATA-01

| Ursprung | Python-Generator des Teams (gen_v2.py); kein einziger echter Datensatz |
| --- | --- |
| Erzeugung | 11.11.2026, Startwert 20261111, Parameter im Register; jederzeit gleich reproduzierbar |
| Grenzen | Kunden, die gar nicht fragen, fehlen; Proxy: Absage = verlorene Nachfrage |
| Geeignet für | Format, Schlüssel und Auswertung testen; nicht als Beleg für das Absagevolumen |

7

> Notizen: Die Pizzeria ist fiktiv, deshalb haben wir den ersten Datenausschnitt mit einem Python-Skript erzeugt. Das steht offen im Provenance Register: wer ihn erzeugt hat, wann, mit welchen Parametern und mit welchem Startwert. So kann jede Person genau dieselbe Datei wieder erzeugen. Wichtig ist auch, wofür die Daten taugen: zum Testen von Format und Auswertung, nicht als Beweis, wie viele Absagen es wirklich gibt.


## Folie 8

Technisch nutzbar, fachlich ungeprüft: Gap-Status bleibt «ungeprüft»

| Kriterium | Technischer Test | Fachlich |
| --- | --- | --- |
| AK-1 Uhrzeit und Kanal | erfüllt: 52 von 52 | ungeprüft |
| AK-2 Grund | gesamt 92 %; SRC-01 allein nur 78 % (14 von 18) | ungeprüft |
| AK-3 Nachfrage | erfüllt: 394 + 52 = 446, Join für 40 von 40 Zeilen | ungeprüft |

Beschaffungserfolg und Schliessung der Evidenzlücke sind zwei verschiedene Prüfungen.

8

> Notizen: Wir haben den Ausschnitt gegen die drei Kriterien getestet. Uhrzeit und Kanal sind überall vorhanden. Der Grund ist insgesamt bei 92 Prozent, bei der Erfassung von Hand aber nur bei 78 Prozent. Das zeigt schon jetzt, worauf wir im Pilot achten müssen. Die Nachfrage lässt sich berechnen: 394 angenommene plus 52 abgelehnte Bestellungen. Trotzdem bleibt der Gap-Status ungeprüft, weil die Daten nicht echt sind. Daten zu haben heisst noch nicht, dass die Lücke geschlossen ist.


## Folie 9

Auch die übrigen zehn Lücken haben eine Quelle, G-02 ist das Muster

| Gap | Lücke | Quelle (Kurzform) | Status |
| --- | --- | --- | --- |
| G-01 | Telefonbestellungen fehlen | Kürzel «T» auf dem Bon, Übertrag in die Kasse | nächster Sourcing-Zyklus |
| G-03 | Fertig-Zeit fehlt | «Fertig»-Taste in der Kasse, ohne Login | nächster Sourcing-Zyklus |
| G-04 | Kein Teigprotokoll | Formular in der Küche | nächster Sourcing-Zyklus |
| G-05 | Wetterprognose nicht archiviert | MeteoSchweiz; Prognose am Mittwoch notieren | nächster Sourcing-Zyklus |
| G-06 | Doppelerfassung Kasse/App | Abgleich über Bestellnummer | Woche 9 (Pipeline) |
| G-07 | Ist-Besetzung | Zeile auf der Strichliste: Personen pro Stunde | nächster Sourcing-Zyklus |
| G-08 | Küchenkapazität | aus G-03 und G-07 berechnet | nach G-03 und G-07 |
| G-09 | Reaktion auf Wartezeit | Plattform fragen, sonst Feldexperiment | später |
| G-10 | Bewertungen | nur als Indiz (einschränken) | laufend |
| G-11 | Gründe bei Sonne | qualitativ erfragen (verzichten auf Daten) | später |

Dieselbe Gap-ID in Data Gap Map, Sourcing Plan, Register und Datenausschnitt. Details im Anhang der Abgabe.

9

> Notizen: Wir haben elf Lücken, und für jede steht fest, woher die Daten kommen sollen. Hier sind die anderen zehn in Kurzform. Zum Beispiel bekommen Telefonbestellungen ein T auf den Bon, und die Wetterprognose notieren wir jeden Mittwoch. Der Auftrag verlangt, eine priorisierte Lücke vollständig durchzuarbeiten. Das ist G-02. Die anderen folgen im nächsten Durchgang nach demselben Muster, und jede behält in allen Dokumenten dieselbe ID.


## Folie 10

Nächste Schritte

13./14.11.

Pilot startet

Absagen auf Bon und Strichliste, Export aus den Portalen

23.11.

Auswertung

AK-1 bis AK-3 mit echten Daten prüfen, Gap-Status neu setzen

Woche 9

Pipeline

DATA-01 und DATA-02 laden, Schlüssel mit den Kassendaten harmonisieren

> Notizen: Am Freitag startet der Pilot. Am 23. November prüfen wir die Kriterien mit echten Daten und setzen den Gap-Status neu. In Woche 9 bauen wir mit diesen Dateien die Pipeline und gleichen die Schlüssel mit den Kassendaten ab. Danke, gibt es Fragen?
