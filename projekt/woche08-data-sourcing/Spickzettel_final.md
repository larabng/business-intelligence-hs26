# Spickzettel_final

```
Spickzettel Präsentation Woche 8: Pizzeria Da Luigi (G-02)
Finale Version, Stand 12. November 2026. Passt zu den 10 Folien der Präsentation.

Roter Faden
Lücke G-02 → drei Quellenkandidaten (SRC) → Bewertung, Bias, Datenschutz → Entscheid und Fallback →
Datenausschnitt (DATA) → Prüfung → Gap-Status. Jeder Schritt verweist auf dieselbe Gap-ID.
Das Beispiel, das immer passt: Die Kasse zählt nur angenommene Bestellungen. Wenn wir um 19 Uhr am Telefon Nein
sagen, sieht das niemand. Deshalb wirkt die Nachfrage genau dann zu klein, wenn am meisten los ist.

Folie für Folie
 Nr.    Folie               Kernaussage                      Was man sagt
 1      Titel               Wir zeigen, wie wir die          Letzte Woche haben wir in der Data Gap Map gezeigt,
                            wichtigste Datenlücke            welche Daten fehlen. Heute zeigen wir für die wichtigste
                            schliessen wollen.               Lücke, G-02, woher die Daten kommen sollen, wie wir die
                                                             Quellen geprüft haben und was unser erster
                                                             Datenausschnitt zeigt.
 2      Warum G-02          Die Kasse zählt nur              Die Kasse zählt nur Bestellungen, die wir annehmen. Wenn
                            angenommene Bestellungen.        wir am Freitagabend um 19 Uhr am Telefon Nein sagen,
                            Absagen sieht niemand.           steht das nirgends. Die Nachfrage wirkt also genau dann zu
                                                             klein, wenn am meisten los ist. Darauf bauen aber zwei
                                                             Entscheide auf: am Mittwoch die Aushilfen, am Vortag die
                                                             Teigmenge. Rechts stehen die drei Akzeptanzkriterien, also
                                                             ab wann die Lücke als geschlossen gilt.
 3      Drei Kandidaten     Pro Quelle ein Canvas: eigene    Wir haben drei mögliche Quellen geprüft, jede mit einem
                            Liste, Plattform-Export,         eigenen Canvas. Erstens: Der Service notiert jede Absage
                            Anrufprotokoll.                  auf dem Bon oder einer Strichliste. Zweitens: Just Eat und
                                                             Uber Eats liefern die abgelehnten App-Bestellungen als
                                                             Export. Drittens: Die Telefonanlage zeigt verpasste Anrufe.
                                                             Das dritte ist nur ein Hinweis, denn ein Anruf ist noch keine
                                                             Bestellung.
 4      Bewertung           Zuerst die Muss-Kriterien. Ein   Bewertet wird in Stufen. Zuerst kommen die Muss-Kriterien:
                            guter Rest rettet eine Quelle    Dürfen wir auf die Daten zugreifen, dürfen wir sie nutzen,
                            nicht.                           und messen sie überhaupt das Richtige? Die eigene Liste
                                                             erfüllt alles. Der Plattform-Export geht nur ohne Namen und
                                                             Adressen. Beim Anrufprotokoll ist die Nutzung ungeklärt,
                                                             weil Telefonnummern Personendaten sind. Deshalb stellen
                                                             wir es zurück, egal wie gut es sonst wäre.
 5      Bias und            Jede Quelle verzerrt anders.     Keine Quelle ist neutral. Bei der eigenen Liste vergisst man
        Datenschutz         Zwei unterschätzen, eine         Einträge genau im grössten Stress, also zählen wir zu wenig.
                            überschätzt.                     Bei der Plattform entsteht im Modus «ausgelastet» gar
                                                             keine Bestellung, also auch zu wenig. Das Anrufprotokoll
                                                             zählt zu viel, weil manche dreimal anrufen. Zu jeder
                                                             Verzerrung haben wir eine Prüfung festgelegt, zum Beispiel
                                                             eine Parallelzählung in zwei Spitzenstunden.
 6      Entscheid und       Wir kombinieren SRC-01 und       Wir nehmen die eigene Liste und den Plattform-Export
        Fallback            SRC-02. Pilot an zwei            zusammen, weil sie verschiedene Kanäle abdecken: Telefon
                            Wochenenden.                     und vor Ort die eine, die Apps die andere. Der Pilot läuft am
                                                             13. und 14. sowie am 20. und 21. November, jeweils von 17
                                                             bis 22 Uhr. Am 23. November werten wir aus. Und wenn
                                                             etwas nicht klappt, haben wir einen Plan B: Liefert die
                                                             Plattform keinen Export, übertragen wir die Absagen von
                                                             Hand aus dem Portal.
 Nr.    Folie                 Kernaussage                     Was man sagt
 7      Provenance            Der Datenausschnitt ist         Die Pizzeria ist fiktiv, deshalb haben wir den ersten
        Register              synthetisch und überall so      Datenausschnitt mit einem Python-Skript erzeugt. Das steht
                              gekennzeichnet.                 offen im Provenance Register: wer ihn erzeugt hat, wann,
                                                              mit welchen Parametern und mit welchem Startwert. So
                                                              kann jede Person genau dieselbe Datei wieder erzeugen.
                                                              Wichtig ist auch, wofür die Daten taugen: zum Testen von
                                                              Format und Auswertung, nicht als Beweis, wie viele
                                                              Absagen es wirklich gibt.
 8      Prüfung und Gap-      Technisch nutzbar, fachlich     Wir haben den Ausschnitt gegen die drei Kriterien getestet.
        Status                ungeprüft. Gap-Status:          Uhrzeit und Kanal sind überall vorhanden. Der Grund ist
                              ungeprüft.                      insgesamt bei 92 Prozent, bei der Erfassung von Hand aber
                                                              nur bei 78 Prozent. Das zeigt schon jetzt, worauf wir im Pilot
                                                              achten müssen. Die Nachfrage lässt sich berechnen: 394
                                                              angenommene plus 52 abgelehnte Bestellungen. Trotzdem
                                                              bleibt der Gap-Status ungeprüft, weil die Daten nicht echt
                                                              sind. Daten zu haben heisst noch nicht, dass die Lücke
                                                              geschlossen ist.
 9      Übrige zehn           Alle elf Lücken haben eine      Wir haben elf Lücken, und für jede steht fest, woher die
        Lücken                Quelle. G-02 ist das            Daten kommen sollen. Hier sind die anderen zehn in
                              ausgearbeitete Beispiel.        Kurzform. Zum Beispiel bekommen Telefonbestellungen ein
                                                              T auf den Bon, und die Wetterprognose notieren wir jeden
                                                              Mittwoch. Der Auftrag verlangt, eine priorisierte Lücke
                                                              vollständig durchzuarbeiten. Das ist G-02. Die anderen
                                                              folgen im nächsten Durchgang nach demselben Muster, und
                                                              jede behält in allen Dokumenten dieselbe ID.
 10     Nächste Schritte      Pilot starten, auswerten, in    Am Freitag startet der Pilot. Am 23. November prüfen wir
                              Woche 9 die Pipeline bauen.     die Kriterien mit echten Daten und setzen den Gap-Status
                                                              neu. In Woche 9 bauen wir mit diesen Dateien die Pipeline
                                                              und gleichen die Schlüssel mit den Kassendaten ab. Danke,
                                                              gibt es Fragen?


Fragen, die kommen können
Warum nur G-02 im Detail?
Der Arbeitsauftrag verlangt, eine priorisierte Lücke vollständig durchzuarbeiten: Canvas, Bewertung, Datenausschnitt,
Prüfung. G-02 verzerrt die Nachfrage am stärksten. Für die anderen zehn Lücken steht die Quelle fest (Folie 9), sie
folgen nach demselben Muster.
Was heisst «dieselbe Gap-ID in allen Artefakten»?
Eine Lücke heisst überall gleich. G-02 ist in der Data Gap Map, im Sourcing Plan, im Register und in der CSV dieselbe
Lücke. Es heisst nicht, dass es nur eine Lücke geben darf.
Warum sind die Daten nicht echt?
Die Pizzeria ist ein fiktiver Fall. Darum ist der Ausschnitt synthetisch, überall so gekennzeichnet und mit Skript und
Startwert reproduzierbar.
Warum ist der Gap-Status nicht «erfüllt»?
Technisch stimmen Format und Schlüssel. Fachlich lässt sich mit erfundenen Daten nichts belegen. Erst der Pilot mit
echten Daten kann die Lücke schliessen.
Was bedeuten die 78 % beim Grund?
Bei der Erfassung von Hand fehlt der Grund bei 4 von 18 Absagen. Verlangt sind 90 %. Im Pilot müssen wir also das
Formular einfach halten, zum Beispiel mit Gründen zum Ankreuzen.
Warum fällt das Anrufprotokoll weg?
Telefonnummern sind Personendaten, die Nutzung ist ungeklärt. Ausserdem ist ein verpasster Anruf noch keine
Bestellung. Es bleibt als Hinweis im Fallback.
Warum Freitag und Samstag?
So steht es im System Charter und im Mission Brief: Die Spitze ist am Freitag- und Samstagabend. Frühere Entwürfe
mit Samstag und Sonntag haben wir angepasst.
Zahlen zum Merken
52 Absagen an 4 Abenden (18 Kasse, 34 App) · 394 angenommene Bestellungen · Nachfrage 446 · Uhrzeit und Kanal 52
von 52 · Grund 92 % gesamt, 78 % bei SRC-01 · Pilot 13./14. und 20./21. November · Auswertung 23. November
```
