# Spickzettel Präsentation Woche 8
```
Spickzettel Präsentation Woche 8: Pizzeria Da Luigi




Spickzettel Präsentation Woche 8: Pizzeria Da
Luigi
  ​Nov 3, 2026         · ​@Lara Bangerter


Worum es geht
In Woche 7 haben wir mit der Data Gap Map gezeigt, welche Daten für die
Wochenendplanung fehlen (Lücken G-01 bis G-11). In Woche 8 zeigen wir, wie wir diese
Lücken schliessen: woher die Daten kommen, wer sie erfasst, was es kostet und wie wir
Herkunft und Datenschutz sichern.

Der rote Faden für die ganze Präsentation: Jede Datenquelle (SP) gehört zu einer Lücke
(G), und jede Lücke gehört zu einer Informationsanforderung (IR). Wenn eine Frage
kommt, kann man fast immer über diese Kette antworten.

Das Beispiel, das man immer erzählen kann: Die Kasse zählt nur angenommene
Bestellungen. Wenn wir am Telefon ablehnen, weil der Ofen voll ist, sieht das niemand.
Deshalb unterschätzen wir die Nachfrage genau dann, wenn sie am grössten ist.


Folie für Folie

  Folie                                           Kernaussage                     Was man sagt

  1 Titel                                         Wir stellen den Data Sourcing   «Letzte Woche haben wir
                                                  Plan und das Provenance         gezeigt, welche Daten fehlen.
                                                  Register vor.                   Heute zeigen wir, wie wir sie
                                                                                  beschaffen.»

  2 Ausgangslage                                  Jeden Donnerstag                Die vier IR kurz vorlesen.
                                                  entscheidet die Pizzeria über   Erwähnen: Lieferung läuft über
                                                  Teig, Aushilfen und App-        Just Eat und Uber Eats, Telefon
                                                  Wartezeit. Dafür braucht es     ist Abholung. Der Engpass ist
                                                  vier Informationen (IR-01 bis   der Ofen, deshalb zählen wir
                                                  IR-04).                         Pizzen statt Bestellungen.




                                                                                                             Page 1 of 5
Spickzettel Präsentation Woche 8: Pizzeria Da Luigi




  Folie                                           Kernaussage                     Was man sagt

  3 Sourcing Plan: Quellen                        Jede der 11 Lücken bekommt      Zwei Beispiele erklären, nicht
  und Technik                                     eine Datenquelle (SP-01 bis     alle Zeilen vorlesen. SP-01:
                                                  SP-11).                         Telefonbestellungen bekommen
                                                                                  ein «T» auf dem Bon, damit man
                                                                                  sie in der Kasse erkennt. SP-04:
                                                                                  Der Küchenchef notiert im
                                                                                  Teigprotokoll, wie viel Teig
                                                                                  angesetzt wurde und wie viel
                                                                                  übrig blieb.

  4 Verantwortung und                             Jede Quelle hat eine            Beispiel SP-01: Erst wenn 4
  Akzeptanz                                       verantwortliche Person,         Wochenenden lang mindestens
                                                  einen Start und eine            95 % der Telefonbestellungen in
                                                  Schwelle, ab wann sie als gut   der Kasse stehen, gilt die Lücke
                                                  genug gilt.                     als geschlossen.

  5 Zugang, Kosten,                               Die Erfassung kostet vor        Kasse und Plattformen sind
  Qualität                                        allem Arbeitszeit, geschätzt    gute Quellen. Die Listen in der
                                                  rund 35 Minuten pro             Küche sind schwächer, weil sie
                                                  Wochenende.                     im Stress vergessen werden.
                                                                                  Bewertungen nutzen wir nur als
                                                                                  Zusatzindiz.

  6 Provenance Register                           Für jeden Datensatz ist         So lässt sich jede Zahl in der
                                                  festgehalten, woher er          Prognose bis zur Quelle
                                                  kommt, wer ihn erfasst, wo er   zurückverfolgen. Beispiel PR-05:
                                                  liegt und was wir damit         Die Wetterprognose wird am
                                                  dürfen.                         Donnerstag gespeichert, weil
                                                                                  MeteoSchweiz später nur noch
                                                                                  das gemessene Wetter liefert.

  7 Datenschutz und                               Wir werten keine                Namen und Telefonnummern
  Ethik                                           Personendaten aus.              werden beim Export gelöscht.
                                                                                  Die Fertig-Taste hat kein Login,
                                                                                  damit niemand einzeln
                                                                                  kontrolliert wird. Bias:
                                                                                  Abgelehnte Anrufe sind
                                                                                  unsichtbar, deshalb geben wir
                                                                                  die Prognose als Spanne an.




                                                                                                               Page 2 of 5
Spickzettel Präsentation Woche 8: Pizzeria Da Luigi




  Folie                                           Kernaussage                     Was man sagt

  8 Erster                                        Der erste Export aus Kasse      Telefon ist nicht getrennt,
  Datenausschnitt                                 und Plattformen zeigt genau     Absagen gibt es nur von den
                                                  die Lücken aus Woche 7.         Plattformen, und die Prognose
                                                                                  vom Donnerstag fehlt. Diese
                                                                                  drei Lücken schliessen SP-01,
                                                                                  SP-02 und SP-06.

  9 Reihenfolge                                   Wir starten mit dem, was am     Die Wetterprognose muss ab
                                                  meisten bringt und am           sofort jeden Donnerstag notiert
                                                  wenigsten kostet.               werden, weil man sie nicht
                                                                                  nachträglich bekommt. Eine
                                                                                  erste Prognose gibt es nach 4
                                                                                  bis 6 Wochenenden.

  10 Fallback                                     Für die wichtigsten Risiken     Ein Beispiel nennen, etwa: Hat
                                                  gibt es einen Plan B.           die Kasse keine Fertig-Taste,
                                                                                  notiert die Küche die Zeit von
                                                                                  Hand auf dem Bon. Abschluss:
                                                                                  In Woche 9 bauen wir damit
                                                                                  Pipeline und Datenmodell.




Begriffe einfach erklärt

  Begriff                                              Bedeutung

  IR (Informationsanforderung)                         Eine Information, die für einen Entscheid
                                                       gebraucht wird, z. B. IR-01 Nachfrage pro Stunde
                                                       und Kanal.

  G (Data Gap, Lücke)                                  Unterschied zwischen dem, was wir wissen
                                                       müssten, und dem, was die Daten zeigen. Kommt
                                                       aus der Data Gap Map (Woche 7).

  SP (Sourcing-Punkt)                                  Eine Zeile im Data Sourcing Plan: woher die Daten
                                                       für eine Lücke kommen.

  PR (Provenance-Eintrag)                              Eine Zeile im Provenance Register: Herkunft,
                                                       Erfasser, Speicherort und Rechte eines
                                                       Datensatzes.

  Konstrukt / Proxy                                    Konstrukt ist das, was wir eigentlich messen wollen
                                                       (Nachfrage). Proxy ist das, was wir messen können
                                                       (angenommene Bestellungen).



                                                                                                             Page 3 of 5
Spickzettel Präsentation Woche 8: Pizzeria Da Luigi




  Begriff                                             Bedeutung

  Primärerhebung                                      Wir erfassen die Daten selbst, z. B. mit einer Liste
                                                      oder einem Kürzel auf dem Bon.

  Instrumentierung                                    Ein System wird so ergänzt, dass es etwas
                                                      automatisch misst, z. B. die Fertig-Taste in der
                                                      Kasse.

  Systemexport                                        Daten, die schon in einem System liegen, werden
                                                      herausgezogen, z. B. CSV aus der Kasse.

  Feldexperiment                                      Etwas im echten Betrieb gezielt verändern und
                                                      vergleichen, z. B. die angezeigte Wartezeit (SP-09).

  Akzeptanzkriterium                                  Die Schwelle, ab der eine Quelle als gut genug gilt,
                                                      z. B. ≥ 95 %.

  Lineage                                             Der nachvollziehbare Weg einer Zahl von der
                                                      Quelle bis zur Prognose.

  Bias                                                Systematische Verzerrung. Bei uns: Abgelehnte
                                                      Bestellungen fehlen, die Nachfrage wirkt kleiner,
                                                      als sie ist.

  revDSG / ArGV 3                                     Schweizer Datenschutzgesetz bzw. Verordnung
                                                      zum Arbeitsgesetz, die Verhaltensüberwachung
                                                      von Mitarbeitenden verbietet.




Mögliche Fragen und Antworten

  Frage                                                               Antwort

  Warum zählt ihr Pizzen und nicht                                    Der Ofen ist der Engpass. Eine Bestellung
  Bestellungen?                                                       mit vier Pizzen belastet ihn viermal so stark
                                                                      wie eine mit einer.

  Warum reichen die Kassendaten nicht?                                Die Kasse zählt nur angenommene
                                                                      Bestellungen. Abgelehnte Anrufe fehlen,
                                                                      also wird die Nachfrage genau in den
                                                                      Spitzenstunden unterschätzt.




                                                                                                               Page 4 of 5
Spickzettel Präsentation Woche 8: Pizzeria Da Luigi




  Frage                                               Antwort

  Was ist der Wartezeit-Test?                         An einigen Wochenenden zeigt die App die
                                                      realistische, längere Wartezeit an. Wir
                                                      vergleichen, ob dann weniger bestellt wird
                                                      als an Wochenenden mit der üblichen
                                                      Anzeige.

  Warum speichert ihr die Wetterprognose?             Entschieden wird am Donnerstag mit der
                                                      Prognose. MeteoSchweiz liefert später nur
                                                      das gemessene Wetter. Ohne Notiz wüssten
                                                      wir nicht, was wir beim Entscheid wussten.

  Ist das nicht Überwachung der                       Nein. Die Fertig-Taste hat kein Login und
  Mitarbeitenden?                                     wird nur pro Stunde ausgewertet. Einzelne
                                                      Personen sind nicht erkennbar.

  Was kostet das Ganze?                               Vor allem Arbeitszeit, geschätzt rund 35
                                                      Minuten pro Wochenende plus 30 Minuten
                                                      Aufbereitung am Montag.

  Was passiert, wenn die Erfassung im Stress          Das Wochenende wird als unvollständig
  nicht klappt?                                       markiert und nicht für die Prognose
                                                      verwendet.

  Wann gibt es eine erste Prognose?                   Nach 4 bis 6 erfassten Wochenenden.
                                                      Vorher geben wir nur eine Spanne an.

  Warum nutzt ihr Bewertungen nur als                 Es gibt wenige Bewertungen, eher von
  Zusatzindiz?                                        unzufriedenen Kunden, und sie erscheinen
                                                      verzögert. Die Verspätung in Minuten ist ein
                                                      besserer Messwert.




                                                                                              Page 5 of 5
```
