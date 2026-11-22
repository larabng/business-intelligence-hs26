# abgabewoche7

# Intelligence-Analyse: Target-centric Approach – Restaurant

Wochenendnachfrage und Kapazitätsplanung nach dem Modell von Clark (2013)

**Ausgangsproblem**

Am Wochenende ist die Nachfrage hoch und schwer vorherzusagen. Kommen wir mit den Bestellungen nicht nach, werden sie zu spät fertig oder müssen abgelehnt werden. Verspätete Bestellungen führen zu schlechten Bewertungen, und schlechte Bewertungen kosten uns künftige Kunden. Das eigentliche Risiko ist also nicht eine einzelne verlorene Bestellung, sondern der langfristige Verlust von Kunden.

<img src="media-abgabewoche7/media/image1.png" style="width:6.04167in;height:4.27083in" />

*Abb.: Intelligence analysis: a target-centric approach, angewendet auf das Restaurant (nach Clark, 2013)*

# Information Requirements Canvas – Restaurant

Informationsbedarf für die Wochenendplanung (Teig, Aushilfen, Annahme von Bestellungen)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>1 Systemzweck</strong></p>
<p><em>Welchen Beitrag soll das sozio-technische System leisten?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<p>Genug Teig und Personal am Wochenende, damit möglichst viele Bestellungen angenommen und rechtzeitig fertig werden. So vermeiden wir schlechte Bewertungen und verlieren keine Kunden, bei minimalem Teigverderb und Personalkosten.</p></th>
<th><p><strong>2 Entscheidung</strong></p>
<p><em>Welche konkrete Entscheidung muss getroffen werden?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<ul>
<li><p>Wie viel Teig wird für Sa/So angesetzt?</p></li>
<li><p>Wie viele Aushilfen pro Wochenendschicht?</p></li>
<li><p>Wird eine App-/Telefonbestellung angenommen, mit längerer Wartezeit angenommen oder abgelehnt?</p></li>
</ul></th>
<th><p><strong>3 Entscheidungsträger</strong></p>
<p><em>Wer oder was trifft diese Entscheidung?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<ul>
<li><p>Küchenchef: Teigmenge, Annahme/Ablehnung, App-Wartezeit</p></li>
<li><p>Geschäftsführer: Anzahl Aushilfen</p></li>
<li><p>Unterstützt durch Kassen- und App-Bestelldaten</p></li>
</ul></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>4 Auslöser und Zeitpunkt</strong></p>
<p><em>Wann entsteht die Entscheidungssituation?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<ul>
<li><p>Aushilfen: Sonntag der Vorwoche (Schichtplan)</p></li>
<li><p>Teig: Donnerstag für Sa, Freitag für So</p></li>
<li><p>Annahme/Ablehnung: laufend im Service, bei jeder neuen App- oder Telefonbestellung</p></li>
</ul></td>
<td><p><strong>5 Handlungsalternativen</strong></p>
<p><em>Zwischen welchen möglichen Handlungen wird entschieden?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<ul>
<li><p>Teig: reduzierte, Standard- oder erhöhte Menge</p></li>
<li><p>Aushilfen: keine, 1, 2+ oder Person auf Abruf</p></li>
<li><p>Bestellung: annehmen, mit erhöhter Wartezeit annehmen, ablehnen (zuerst Telefon, dann App)</p></li>
</ul></td>
<td><p><strong>6 Entscheidungsrelevante Unsicherheit</strong></p>
<p><em>Was ist zum Entscheidungszeitpunkt nicht hinreichend bekannt?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<ul>
<li><p>Nachfrage pro Tag, Stunde und Kanal</p></li>
<li><p>Einfluss von Wetter und Events in der Nähe</p></li>
<li><p>Warum Kunden bei gutem Wetter nicht bestellen</p></li>
<li><p>Wie viele Bestellungen die Küche pro Stunde schafft</p></li>
<li><p>Wie Kunden auf lange Wartezeiten reagieren (Bewertung, Abwanderung)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>7 Benötigte Information</strong></p>
<p><em>Welche Aussage über das System reduziert die Unsicherheit?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<p>Erwartete Nachfrage am Wochenende pro Stunde und Kanal (unter Berücksichtigung von Wetter und Events), verglichen mit der Küchenkapazität (Zubereitungszeit, Personal) und dem Teigverderb.</p></td>
<td><p><strong>8 Informationsanforderung</strong></p>
<p><em>Was muss die Information inhaltlich und zeitlich leisten?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<ul>
<li><p>Erwartete Bestellungen je Tag und Stunde, je Kanal</p></li>
<li><p>Bandbreite (min./max.) als Unsicherheit</p></li>
<li><p>Daraus abgeleitet: Teigportionen und Aushilfen pro Schicht</p></li>
<li><p>Live-Auslastung: offene Bestellungen vs. Kapazität</p></li>
<li><p>Verfügbar: Personal So der Vorwoche, Teig Do/Fr, Auslastung in Echtzeit</p></li>
</ul></td>
<td><p><strong>9 Erwartete Wirkung</strong></p>
<p><em>Welche bessere Handlung und Systemwirkung soll ermöglicht werden?</em></p>
<p><strong>Beispiel · Restaurant</strong></p>
<ul>
<li><p>Weniger Teigverderb</p></li>
<li><p>Weniger verspätete Bestellungen</p></li>
<li><p>Weniger abgelehnte Bestellungen</p></li>
<li><p>Bessere Bewertungen und mehr Stammkunden</p></li>
<li><p>Planbare Personalkosten</p></li>
</ul></td>
</tr>
</tbody>
</table>

# Traceability Matrix – Restaurant

Begründungskette vom Systemzweck über BI-Frage, Entscheidung und Informationsanforderung bis zur erwarteten Wirkung

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 12%" />
<col style="width: 13%" />
<col style="width: 16%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Systemzweck</strong></th>
<th><strong>BI-Frage</strong></th>
<th><strong>Entscheidung</strong></th>
<th><strong>Informations­anforderung</strong></th>
<th><strong>Geplantes Datenprodukt</strong></th>
<th><strong>Handlung</strong></th>
<th><strong>Erwartete Wirkung</strong></th>
<th><strong>Evidenzstatus / offene Annahmen</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>S-01</strong></p>
<p>Bestellungen rechtzeitig, möglichst wenige Absagen</p></td>
<td><p><strong>Q-01</strong></p>
<p>Wie viele Bestellungen kommen am Wochenende pro Stunde und Kanal?</p></td>
<td><p><strong>D-01</strong></p>
<p>Wie viele Aushilfen pro Wochenendschicht? (Geschäftsführer, So der Vorwoche)</p></td>
<td><p><strong>IR-01</strong></p>
<p>Nachfrageprognose Sa/So pro Stunde und Kanal (vor Ort, App, Telefon) mit Bandbreite, unter Berücksichtigung von Wetter und Events; verfügbar am Sonntag der Vorwoche</p></td>
<td><p><strong>DP-01</strong></p>
<p>Wöchentlicher Prognose-Report Personalbedarf</p></td>
<td><p><strong>A-01</strong></p>
<p>Aushilfen gemäss Prognose einplanen, bei hoher Bandbreite Person auf Abruf</p></td>
<td><p><strong>W-01</strong></p>
<p>Weniger verspätete Bestellungen, planbare Personalkosten</p></td>
<td><em>Annahme: Wetter und Events erklären die Nachfrage – noch nicht belegt. Telefonbestellungen werden bisher nicht erfasst.</em></td>
</tr>
<tr class="even">
<td><p><strong>S-02</strong></p>
<p>Teigverfügbarkeit sichern bei minimalem Verderb</p></td>
<td><p><strong>Q-02</strong></p>
<p>Wie viel Teig wird am Samstag bzw. Sonntag benötigt?</p></td>
<td><p><strong>D-02</strong></p>
<p>Welche Teigmenge wird angesetzt? (Küchenchef, Do für Sa, Fr für So)</p></td>
<td><p><strong>IR-02</strong></p>
<p>Erwartete Bestellungen pro Tag, umgerechnet in Teigportionen (min./max.), mit aktueller Wetterprognose; verfügbar vor der Teigzubereitung</p></td>
<td><p><strong>DP-02</strong></p>
<p>Teigmengen-Empfehlung</p></td>
<td><p><strong>A-02</strong></p>
<p>Reduzierte, Standard- oder erhöhte Teigmenge ansetzen</p></td>
<td><p><strong>W-02</strong></p>
<p>Weniger Teigverderb, weniger Absagen wegen fehlendem Teig</p></td>
<td><em>Verderbmenge wird heute nicht gemessen; Baseline muss zuerst erhoben werden.</em></td>
</tr>
<tr class="odd">
<td><p><strong>S-01 S-03</strong></p>
<p>Bestellungen rechtzeitig; gute Bewertungen halten, keine Kunden verlieren</p></td>
<td><p><strong>Q-03</strong></p>
<p>Kann die Küche eine neue Bestellung rechtzeitig fertigstellen?</p></td>
<td><p><strong>D-03</strong></p>
<p>Bestellung annehmen, mit längerer Wartezeit annehmen oder ablehnen? (Küchenchef, laufend im Service)</p></td>
<td><p><strong>IR-03</strong></p>
<p>Live-Auslastung: offene Bestellungen vs. Küchenkapazität (Zubereitungszeit, anwesendes Personal), unter Berücksichtigung der Priorität vor Ort › App › Telefon; in Echtzeit</p></td>
<td><p><strong>DP-03</strong></p>
<p>Auslastungsanzeige in der Küche und dynamische Wartezeit in der App</p></td>
<td><p><strong>A-03</strong></p>
<p>App-Wartezeit erhöhen, bei Überlast zuerst Telefon-, dann App-Bestellungen ablehnen</p></td>
<td><p><strong>W-03</strong></p>
<p>Alle angenommenen Bestellungen rechtzeitig, bessere Bewertungen, weniger Kundenverlust</p></td>
<td><em>Annahme: Kunden akzeptieren eine angezeigte Wartezeit eher als eine Verspätung – ungeprüft. Zubereitungszeit pro Bestellung noch nicht gemessen.</em></td>
</tr>
<tr class="even">
<td><p><strong>S-01 S-02 S-03</strong></p>
<p>Rechtzeitige Bestellungen, minimaler Verderb, Kunden halten</p></td>
<td><p><strong>Q-04</strong></p>
<p>Wirken die Massnahmen auf Verspätungen, Absagen, Verderb und Bewertungen?</p></td>
<td><p><strong>D-01 D-02 D-03</strong></p>
<p>Prognose und Schwellenwerte anpassen (Geschäftsführer, Küchenchef)</p></td>
<td><p><strong>IR-04</strong></p>
<p>Verspätungs-, Absage- und Verderbquote pro Wochenende sowie Bewertungen (App, Google); wöchentlich</p></td>
<td><p><strong>DP-04</strong></p>
<p>Wochen-Review mit Kennzahlen</p></td>
<td><p><strong>A-04</strong></p>
<p>Prognosemodell und Annahmeregeln nachjustieren</p></td>
<td><p><strong>W-04</strong></p>
<p>Lernschleife: Wirkung W-01 bis W-03 wird überprüfbar</p></td>
<td><em>Wirkungshypothesen; empirische Prüfung über mehrere Wochenenden nötig.</em></td>
</tr>
</tbody>
</table>

**Vorwärts- und Rückwärtsprüfung**

Vorwärts (vom Systemzweck): Alle drei Entscheidungen aus dem Canvas sind durch eine Informationsanforderung abgedeckt (D-01 → IR-01, D-02 → IR-02, D-03 → IR-03).

Rückwärts (vom Requirement): IR-01 bis IR-03 lassen sich je einer Entscheidung und Wirkung zuordnen. IR-04 stützt keine operative Entscheidung direkt, sondern die Überprüfung der Wirkungshypothesen und die Anpassung von D-01 bis D-03.

*Grenzen: Die Matrix dokumentiert eine Begründungsstruktur, sie beweist nicht, dass die Information die Handlung verbessert. Die Datenprodukte (DP) sind Designvorschläge. Rückkopplungen aus dem Systemmodell bleiben relevant, z. B. dass schlechte Bewertungen die künftige Nachfrage senken.*

# Data Product Canvas – Restaurant

Vom Informationsbedarf zum Datenprodukt (nach Hasan & Legner, 2023): DP-01 bis DP-04 aus der Traceability Matrix als ein Datenprodukt

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th colspan="2"><strong>Data product name:</strong> Wochenend-Kapazitätsplaner</th>
<th colspan="3"><strong>Data product category:</strong> Prognose &amp; Entscheidungsunterstützung</th>
<th colspan="2"><strong>Version:</strong> 1.0 (Entwurf)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td rowspan="2"><p><strong>◈ Key Data Objects</strong></p>
<p><em>Which data objects will be used?</em></p>
<ul>
<li><p>Bestellungen: Zeitpunkt, Kanal (vor Ort, App, Telefon), Artikel, Fertigstellungszeit</p></li>
<li><p>Absagen und Verspätungen</p></li>
<li><p>Teig: angesetzt, verbraucht, verdorben</p></li>
<li><p>Schichten und Personal</p></li>
<li><p>Wetter, Events, Feiertage</p></li>
<li><p>Bewertungen</p></li>
</ul>
<p><em>From which source(s)?</em></p>
<ul>
<li><p>Kassensystem, App-Backend</p></li>
<li><p>Telefon-Strichliste (neu)</p></li>
<li><p>Teigprotokoll Küche (neu)</p></li>
<li><p>Personalplan</p></li>
<li><p>Wetterprognose, Eventkalender</p></li>
<li><p>Google- und App-Bewertungen</p></li>
</ul></td>
<td><p><strong>↻ Key Activities</strong></p>
<p><em>What activities are required to design, develop and deploy?</em></p>
<ul>
<li><p>Telefon- und Teigdaten neu erfassen</p></li>
<li><p>Daten wöchentlich zusammenführen und bereinigen</p></li>
<li><p>Nachfrage pro Tag, Stunde und Kanal prognostizieren</p></li>
<li><p>In Teigportionen und Aushilfen umrechnen</p></li>
<li><p>Live-Auslastung berechnen, App-Wartezeit setzen</p></li>
<li><p>Wochen-Review, Modell nachjustieren</p></li>
</ul></td>
<td colspan="2" rowspan="2"><p><strong>◇ Value Propositions</strong></p>
<p><em>Which information need does it satisfy? What problems does it solve?</em></p>
<p>Wie hoch wird die Nachfrage am Wochenende, und reicht unsere Kapazität? (IR-01 bis IR-04)</p>
<ul>
<li><p>Bestellungen werden zu spät fertig</p></li>
<li><p>Zu viel oder zu wenig Teig</p></li>
<li><p>Personalplanung nach Bauchgefühl</p></li>
<li><p>Schlechte Bewertungen, Kundenverlust</p></li>
</ul>
<p><em>What concrete value will be realized?</em></p>
<ul>
<li><p>Angenommene Bestellungen rechtzeitig fertig</p></li>
<li><p>Weniger Teigverderb</p></li>
<li><p>Kunden sehen vor dem Bestellen eine realistische Wartezeit</p></li>
</ul></td>
<td colspan="2"><p><strong>♡ Consumer Relationships</strong></p>
<p><em>How does the consumer discover it? What support is expected?</em></p>
<ul>
<li><p>Intern eingeführt an der Teamsitzung, kein Katalog nötig</p></li>
<li><p>Kurze Schulung für Küchenchef und Service</p></li>
<li><p>Feedback nach jedem Wochenende, Anpassung im Wochen-Review</p></li>
</ul></td>
<td rowspan="2"><p><strong>♧ Data Product Consumers</strong></p>
<p><em>Who are the main consumers?</em></p>
<p>(i) Intern: Geschäftsführer, Küchenchef, Servicepersonal</p>
<p>(ii) Extern: App-Kunden (sehen die Wartezeit)</p>
<p><em>Major use cases</em></p>
<ul>
<li><p>Geschäftsführer: Schichtplan am Sonntag der Vorwoche</p></li>
<li><p>Küchenchef: Teigmenge Do/Fr, Bestellungen live annehmen oder ablehnen</p></li>
<li><p>Service: Telefonbestellungen annehmen oder ablehnen</p></li>
<li><p>Kunden: entscheiden mit realistischer Wartezeit</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>⚙ Key Resources</strong></p>
<p><em>(i) People</em></p>
<ul>
<li><p>Geschäftsführer als Product Owner</p></li>
<li><p>Küchenchef: fachliche Prüfung</p></li>
<li><p>Service: Telefonerfassung</p></li>
</ul>
<p><em>(ii) System</em></p>
<ul>
<li><p>Kassensystem, App mit Schnittstelle</p></li>
<li><p>Excel oder Power BI</p></li>
<li><p>Tablet in der Küche</p></li>
</ul></td>
<td colspan="2"><p><strong>→ Data Product Delivery</strong></p>
<p><em>In which format? On which interface?</em></p>
<ul>
<li><p>Prognose-Report wöchentlich (So) per E-Mail/PDF</p></li>
<li><p>Teigmengen-Empfehlung Do/Fr</p></li>
<li><p>Live-Dashboard auf Tablet in der Küche</p></li>
<li><p>Automatische Wartezeit in der App</p></li>
</ul></td>
</tr>
<tr class="odd">
<td colspan="3"><p><strong>▣ Cost Structure</strong></p>
<p><em>What costs are involved?</em></p>
<ul>
<li><p>Aufbau: Erfassung einrichten, Prognose aufsetzen</p></li>
<li><p>Laufend: Zeit für Datenpflege und Wochen-Review</p></li>
<li><p>Lizenzen (z. B. Power BI), Anpassung der App, Tablet</p></li>
<li><p>Schulung des Teams</p></li>
</ul></td>
<td colspan="4"><p><strong>↗ Benefits</strong></p>
<p><em>What benefits (financial or non-financial)?</em></p>
<ul>
<li><p>Kostenersparnis durch weniger Teigverderb</p></li>
<li><p>Mehr Umsatz durch weniger Absagen</p></li>
<li><p>Bessere Bewertungen und mehr Stammkunden</p></li>
<li><p>Planbare Personalkosten, weniger Risiko</p></li>
</ul></td>
</tr>
</tbody>
</table>

**Desirability:** Löst das Hauptproblem (Verspätungen → schlechte Bewertungen → Kundenverlust) für Geschäftsführer, Küchenchef und Kunden.

**Feasibility:** Kassen- und App-Daten sind vorhanden; Telefon- und Teigdaten müssen erst erfasst werden.

**Viability:** Tragfähig, wenn die Ersparnis bei Verderb und der Gewinn an Kunden den laufenden Pflegeaufwand übersteigt; im Wochen-Review zu prüfen.

# 
