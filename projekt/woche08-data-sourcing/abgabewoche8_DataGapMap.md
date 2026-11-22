# abgabewoche8_DataGapMap

Data Gap Map: Pizzeria Da Luigi

Prüft, ob die verfügbaren Daten die Informationsanforderungen für die Wochenendplanung ausreichend stützen, und legt fest, wie die relevanten Lücken geschlossen werden.

**1 Entscheidung und Informationsanforderungen**

**Entscheidung:** Jeweils am Donnerstag für das kommende Wochenende (Fr–So) festlegen, wie viel Teig angesetzt wird, wie viele Aushilfen pro Schicht eingeplant werden und welche Wartezeit die App anzeigt.

**Zweck:** Möglichst wenige Absagen, alle angenommenen Bestellungen rechtzeitig. Priorität der Kanäle: vor Ort › App › Telefon. Teig muss 2 Tage im Voraus angesetzt werden.

| **IR**    | **Informationsanforderung (Kurzform)**                                                                                                 | **Stützt Entscheidung**       |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| **IR-01** | Erwartete Nachfrage pro Wochenendtag und Stunde, je Bestellkanal (vor Ort, App, Telefon), unter Berücksichtigung von Wetter und Events | Aushilfen, Teigmenge          |
| **IR-02** | Benötigte Teigmenge für das Wochenende, 2 Tage im Voraus                                                                               | Teig ansetzen                 |
| **IR-03** | Küchenkapazität pro Stunde im Vergleich zur erwarteten Nachfrage                                                                       | Aushilfen, App-Wartezeit      |
| **IR-04** | Absagen, Verspätungen und ihre Wirkung auf die Kundenzufriedenheit                                                                     | Wirkungskontrolle der Planung |

Verfügbare Quellen gemäss Dateninventar: Kasse (POS), App-Backend, Schichtplan, Google- und App-Bewertungen, Veranstaltungskalender der Gemeinde, MeteoSchweiz (Open Data).

**2 Konstrukt, Messwert und Proxy**

Die Daten werden zuerst auf Messvalidität geprüft: Bildet der verfügbare Messwert überhaupt das ab, was die Entscheidung braucht? Saubere Daten über das falsche Merkmal bleiben ungeeignete Evidenz.

| **IR**    | **Konstrukt (was gemeint ist)**                                                     | **Messwert / Proxy (was vorliegt)**         | **Annahme und wann sie versagt**                                                                                                                                                                                  |
|-----------|-------------------------------------------------------------------------------------|---------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **IR-01** | Wochenendnachfrage: alle Bestellwünsche, auch abgelehnte und nie zustande gekommene | Angenommene Bestellungen in Kasse und App   | Annahme: Bestellungen ≈ Nachfrage. Versagt genau in Spitzenstunden, wenn abgelehnt wird, das Telefon besetzt ist oder Kunden wegen der Wartezeit abbrechen. Die Nachfrage wird dann systematisch unterschätzt.    |
| **IR-02** | Teigbedarf für das Wochenende                                                       | Verkaufte Pizzen × Teig pro Pizza           | Annahme: Verkäufe zeigen den Bedarf. Versagt, wenn der Teig ausgeht: Dann sind die Verkäufe durch den Teig gedeckelt und die Prognose bestätigt die zu knappe Menge selbst.                                       |
| **IR-03** | Küchenkapazität: Pizzen pro Stunde bei gegebener Besetzung                          | Bestellungen pro Stunde in Spitzenzeiten    | Annahme: Spitzenwert = Kapazität. Versagt, weil der Wert die Auslastung misst, nicht die Grenze. Ob mehr möglich gewesen wäre, bleibt offen.                                                                      |
| **IR-04** | Servicequalität und Kundenzufriedenheit                                             | Sternebewertungen auf Google und in der App | Annahme: schlechte Wochenenden zeigen sich in Bewertungen. Versagt, weil nur wenige und eher unzufriedene Kunden bewerten und Bewertungen verzögert erscheinen. Direkter Messwert wäre die Verspätung in Minuten. |

**3 A. Evidenz- und Prüftabelle**

Beurteilung: **erfüllt**, **teilweise erfüllt**, **nicht erfüllt** oder **ungeprüft**. Die Schwellen sind aus der Entscheidung abgeleitet und werden nach den ersten Wochenenden überprüft.

| **ID**   | **IR**       | **Evidenz / Akzeptanzkriterium**                                                      | **Prüfdimension**            | **Prüfbefund / Nachweis**                                                                                                 | **Beurteilung / Wirkung**                                                                    |
|----------|--------------|---------------------------------------------------------------------------------------|------------------------------|---------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| **E-01** | IR-01        | Alle Bestellungen mit Kanal und Uhrzeit; ≥ 95 % der Wochenendbestellungen erfasst     | Vollständigkeit              | Kasse und App liefern Zeitstempel. Telefonbestellungen werden nicht als eigener Kanal erfasst, teils nur auf Zetteln.     | **Nicht erfüllt.** Telefonanteil fehlt; Nachfrage und Kanalmix werden unterschätzt.          |
| **E-02** | IR-01        | Jede abgelehnte Bestellung mit Uhrzeit und Grund erfasst                              | Repräsentativität, Validität | Kasse erfasst nur angenommene Bestellungen. App-Absagen liegen im Backend, Ablehnungen vor Ort und am Telefon nirgends.   | **Teilweise erfüllt** (nur App). Spitzen sind systematisch unterschätzt (siehe Abschnitt 2). |
| **E-03** | IR-01        | Historie von ≥ 6 Wochenenden mit unterschiedlichem Wetter und mit/ohne Events         | Repräsentativität            | Kassenhistorie vorhanden. Wetter und Events sind nicht mit den Wochenenden verknüpft.                                     | **Teilweise erfüllt.** Einfluss von Wetter und Events ist nicht schätzbar.                   |
| **E-04** | IR-01        | Jede Bestellung genau einmal gezählt (App-Bestellungen nicht zusätzlich in der Kasse) | Eindeutigkeit, Konsistenz    | Abgleich von Kassen- und App-Export über Bestellnummer noch nicht durchgeführt.                                           | **Ungeprüft.** Risiko einer Überschätzung der Nachfrage.                                     |
| **E-05** | IR-02        | Teig angesetzt, verbraucht und verworfen je Wochenende                                | Vollständigkeit              | Keine Erfassung; Wissen liegt beim Küchenchef.                                                                            | **Nicht erfüllt.** Teigmenge bleibt Schätzung; Engpass und Verschwendung nicht messbar.      |
| **E-06** | IR-01, IR-02 | Daten liegen am Donnerstag (Entscheidungszeitpunkt) vor                               | Aktualität                   | Kassen- und App-Daten tagesaktuell; Wetterprognose und Eventkalender am Donnerstag verfügbar.                             | **Erfüllt** für die vorhandenen Daten.                                                       |
| **E-07** | IR-01, IR-02 | Wetterprognose, wie sie am Donnerstag bekannt war, gespeichert                        | Zeitbezug, Lineage           | MeteoSchweiz liefert rückwirkend nur das gemessene Wetter. Die Prognose zum Entscheidungszeitpunkt wird nicht archiviert. | **Nicht erfüllt.** Ein Modell mit Ist-Wetter wirkt genauer, als es am Donnerstag sein kann.  |
| **E-08** | IR-03, IR-04 | Fertig-Zeit für ≥ 90 % der Bestellungen                                               | Vollständigkeit              | Kasse erfasst Bestellzeit, App die versprochene Zeit. Eine Fertig-Zeit wird nicht erfasst.                                | **Nicht erfüllt.** Kapazität und Verspätungen sind nicht messbar.                            |
| **E-09** | IR-03        | Tatsächliche Küchenbesetzung pro Stunde                                               | Korrektheit                  | Schichtplan zeigt die geplante Besetzung; Ausfälle und Schichttausch werden nicht nachgeführt.                            | **Teilweise erfüllt.** Kapazität pro Person nur unsicher ableitbar.                          |
| **E-10** | IR-03        | Abbruchquote in der App nach Anzeige der Wartezeit                                    | Vollständigkeit              | Ob das App-Backend Abbrüche protokolliert, ist noch nicht geklärt.                                                        | **Ungeprüft.** Wirkung der Wartezeit-Anzeige unbekannt.                                      |
| **E-11** | IR-04        | Bewertungen mit Datum und Sternen, wochenweise zuordenbar                             | Validität, Repräsentativität | Google- und App-Bewertungen einsehbar, aber kein Export; wenige Bewertungen pro Woche.                                    | **Teilweise erfüllt.** Nur als schwaches Indiz nutzbar.                                      |

**Lineage der Prognose:** Kasse- und App-Export → Kanal zuordnen und Duplikate entfernen → mit Wetter und Events verbinden → pro Tag und Stunde aggregieren → Prognose → Teigmenge und Aushilfen. Für jeden Schritt werden Quelle, Regel, Zeitpunkt und Verantwortung festgehalten. Heute ist nur der erste Schritt dokumentiert; die übrigen laufen manuell und ohne festgehaltene Regel.

**4 B. Gap- und Massnahmenregister**

Gap-Typen: **Verfügbarkeit** (Beobachtung fehlt), **Validität** (Proxy nicht hinreichend begründet), **Qualität** (Akzeptanzkriterium nicht erfüllt), **Lineage/Zeit** (Herkunft oder damaliger Wissensstand nicht rekonstruierbar). Die Massnahme folgt aus Risiko und Aufwand, nicht jede Lücke wird durch neue Daten geschlossen.

<table>
<colgroup>
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 7%" />
<col style="width: 10%" />
<col style="width: 27%" />
<col style="width: 10%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Gap</strong></th>
<th><strong>Lücke</strong></th>
<th><strong>Bezug</strong></th>
<th><strong>Typ / Priorität</strong></th>
<th><strong>Massnahme</strong></th>
<th><strong>Verantwortlich</strong></th>
<th><strong>Abschlusskriterium</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>G-01</strong></td>
<td>Telefonbestellungen fehlen</td>
<td><p>IR-01, IR-03</p>
<p>E-01</p></td>
<td>Verfügbarkeit / hoch</td>
<td><strong>Beschaffen:</strong> Jede Telefonbestellung in die Kasse mit Kanal «Telefon». Übergangsweise Strichliste mit Uhrzeit, Anzahl Pizzen, angenommen/abgelehnt.</td>
<td>Service</td>
<td>4 Wochenenden in Folge ≥ 95 % der Telefonbestellungen in der Kasse (Stichprobe gegen Strichliste)</td>
</tr>
<tr class="even">
<td><strong>G-02</strong></td>
<td>Abgelehnte Bestellungen unsichtbar</td>
<td><p>IR-01, IR-04</p>
<p>E-02</p></td>
<td>Validität / hoch</td>
<td><strong>Beschaffen:</strong> Ablehnungen mit Grund (kein Teig, keine Kapazität, Wartezeit zu lang) in Kasse oder auf derselben Liste; App-Absagen aus dem Backend übernehmen.</td>
<td>Service, Küchenchef</td>
<td>Nachfrage = angenommen + abgelehnt pro Stunde berechenbar; Proxy aus Abschnitt 2 neu geprüft</td>
</tr>
<tr class="odd">
<td><strong>G-03</strong></td>
<td>Fertig-Zeit fehlt</td>
<td><p>IR-03, IR-04</p>
<p>E-08</p></td>
<td>Verfügbarkeit / hoch</td>
<td><strong>Beschaffen:</strong> «Fertig»-Klick in der Kasse oder auf dem Küchen-Tablet. Mit Bestellzeit und versprochener Zeit ergibt sich die Verspätung.</td>
<td>Küche</td>
<td>≥ 90 % der Bestellungen mit Fertig-Zeit; Verspätung pro Stunde auswertbar</td>
</tr>
<tr class="even">
<td><strong>G-04</strong></td>
<td>Kein Teigprotokoll</td>
<td><p>IR-02</p>
<p>E-05</p></td>
<td>Verfügbarkeit / hoch</td>
<td><strong>Beschaffen:</strong> Teigprotokoll: Do/Fr angesetzte Portionen, So abends übrig gebliebene und verworfene Portionen.</td>
<td>Küchenchef</td>
<td>6 Wochenenden lückenlos protokolliert; Tage mit Teigengpass markiert</td>
</tr>
<tr class="odd">
<td><strong>G-05</strong></td>
<td>Wetterprognose nicht archiviert, Wetter und Events nicht verknüpft</td>
<td><p>IR-01, IR-02</p>
<p>E-03, E-07</p></td>
<td>Lineage/Zeit / mittel</td>
<td><strong>Beschaffen und verbessern:</strong> Am Donnerstag die Prognose festhalten, nach dem Wochenende das gemessene Wetter (MeteoSchweiz) danebenstellen; Events aus dem Gemeindekalender als Spalte.</td>
<td>Geschäftsführer</td>
<td>Für jedes Wochenende Prognose, Ist-Wetter und Events in derselben Tabelle</td>
</tr>
<tr class="even">
<td><strong>G-06</strong></td>
<td>Mögliche Doppelerfassung Kasse/App</td>
<td><p>IR-01</p>
<p>E-04</p></td>
<td>Qualität / mittel</td>
<td><strong>Verbessern:</strong> Kassen- und App-Export über Bestellnummer abgleichen; Regel festlegen, welche Quelle zählt.</td>
<td>Daten (Daniele)</td>
<td>Duplikatquote gemessen und &lt; 1 %</td>
</tr>
<tr class="odd">
<td><strong>G-07</strong></td>
<td>Ist-Besetzung weicht vom Schichtplan ab</td>
<td><p>IR-03</p>
<p>E-09</p></td>
<td>Qualität / mittel</td>
<td><strong>Verbessern:</strong> Schichtplan nach jedem Wochenende auf die tatsächliche Besetzung korrigieren.</td>
<td>Geschäftsführer</td>
<td>Ist-Besetzung pro Stunde für alle erfassten Wochenenden vorhanden</td>
</tr>
<tr class="even">
<td><strong>G-08</strong></td>
<td>Küchenkapazität unbekannt</td>
<td><p>IR-03</p>
<p>E-08, E-09</p></td>
<td>Validität / mittel</td>
<td><strong>Ändern:</strong> Kapazität nicht aus Spitzen-Bestellungen ablesen, sondern aus Fertig-Zeiten (G-03) und Ist-Besetzung (G-07) ableiten, und zwar nur in Stunden mit Warteschlange.</td>
<td>Geschäftsführer</td>
<td>Kapazität pro Person und Stunde aus ≥ 4 Wochenenden mit Spannweite angegeben</td>
</tr>
<tr class="odd">
<td><strong>G-09</strong></td>
<td>Reaktion der Kunden auf Wartezeit unbekannt</td>
<td><p>IR-03</p>
<p>E-10</p></td>
<td>Verfügbarkeit / mittel</td>
<td><strong>Beschaffen:</strong> Zuerst klären, ob die App Abbrüche protokolliert. Falls nicht: zwei Wochenenden mit unterschiedlicher Wartezeit-Anzeige vergleichen.</td>
<td>App, Geschäftsführer</td>
<td>Abbruchquote je angezeigter Wartezeit bekannt</td>
</tr>
<tr class="even">
<td><strong>G-10</strong></td>
<td>Bewertungen als schwacher Proxy</td>
<td><p>IR-04</p>
<p>E-11</p></td>
<td>Validität / niedrig</td>
<td><strong>Einschränken:</strong> Bewertungen nur ergänzend als Indiz nutzen, nicht als Zielgrösse. Wöchentlich mit Datum und Sternen festhalten, später Export.</td>
<td>Geschäftsführer</td>
<td>Zufriedenheit wird primär über Verspätung (G-03) und Absagen (G-02) beurteilt</td>
</tr>
<tr class="odd">
<td><strong>G-11</strong></td>
<td>Warum bei gutem Wetter weniger bestellt wird</td>
<td>IR-01</td>
<td>Validität / niedrig</td>
<td><strong>Verzichten</strong> auf eine datenbasierte Erklärung: Den Wettereffekt in der Prognose als Zusammenhang nutzen; die Ursache nur qualitativ erfragen (Kurzfrage in der App, Gespräche mit Stammkunden).</td>
<td>Service</td>
<td>Ursache wird im Bericht nicht als belegt ausgegeben</td>
</tr>
</tbody>
</table>

**5 Unsicherheit**

- **Messunsicherheit:** Strichlisten und «Fertig»-Klicks werden im Wochenendstress lückenhaft oder verspätet geführt.

- **Modellunsicherheit:** Auch angenommene plus abgelehnte Bestellungen sind nicht die volle Nachfrage. Wer bei besetztem Telefon aufgibt, bleibt unsichtbar.

- **Abdeckungsunsicherheit:** Wenige Wochenenden; Extremwetter und Grossevents kommen selten vor.

- **Zeitunsicherheit:** Entschieden wird mit der Wetterprognose vom Donnerstag, nicht mit dem späteren Ist-Wetter (G-05).

**Konsequenz:** Bis mindestens 6 Wochenenden erfasst sind, wird die Prognose als Spanne ausgegeben und die Teigmenge mit Puffer geplant.

**6 Priorisierung und Vorgehen**

**Früh beginnen:** Für eine belastbare Prognose braucht es Daten von mehreren Wochenenden, mindestens etwa 4–6, besser mehr und mit unterschiedlichem Wetter. Zuerst starten die Massnahmen mit hoher Priorität und kleinstem Aufwand: G-01 Telefonbestellungen in der Kasse, G-03 Fertig-Zeit und G-04 Teigprotokoll. G-02 läuft auf derselben Liste mit.

**Erfassung im Stress möglich machen:** Am Wochenende ist die Belastung am höchsten. Die Erfassung muss deshalb mit einem Klick in der Kasse oder einem Strich auf einer Liste möglich sein, sonst wird sie im Stress vergessen.

**Danach:** G-05 bis G-09 aufbauen, sobald die ersten Wochenenden erfasst sind. Die Beschaffung im Detail (Zugang, Datenschutz, Kosten) folgt im Data Sourcing Plan.
