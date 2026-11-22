# Abgabe_Woche8_DataSourcingPlan_Provenance_G02_final

Pizzeria Da Luigi · BI HS2026 · Abgabe Woche 9 (Deliverable aus Woche 8, Episoden 15 und 16) · Stand 11. November 2026 · finale Version

Rahmen: Betrachtet werden Freitag- und Samstagabend von 17 bis 22 Uhr, wie in System Charter und BI Mission Brief. App-Bestellungen laufen über Just Eat und Uber Eats, Telefon und vor Ort über die Kasse. Die Pizzeria ist ein fiktiver Fall, deshalb ist der Datenausschnitt synthetisch.

# 1 Ausgangslage: priorisierte Lücke G-02

Aus der Data Gap Map wird G-02 priorisiert: Abgelehnte Bestellungen sind unsichtbar. Die Kasse erfasst nur angenommene Bestellungen, deshalb wird die Nachfrage genau in den Spitzenstunden unterschätzt. G-02 ist eine Validitätslücke mit hoher Priorität und betrifft zwei Informationsanforderungen.

| **Traceability**                 | **Inhalt**                                                                                                                                                              |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Gap-ID**                       | G-02 Abgelehnte Bestellungen unsichtbar (Validität / hoch)                                                                                                              |
| **Informationsanforderung**      | IR-01 Nachfrage pro Tag, Stunde und Kanal · IR-04 Absagen, Verspätungen und Wirkung auf die Kundenzufriedenheit                                                         |
| **Entscheidung**                 | Mittwoch: Aushilfen für Fr und Sa · am Vortag: Teigmenge                                                                                                                |
| **Evidenz aus der Data Gap Map** | E-02: Jede abgelehnte Bestellung mit Uhrzeit und Grund erfasst (heute: teilweise erfüllt, nur App)                                                                      |
| **Akzeptanzkriterien**           | AK-1: ≥ 95 % der Absagen mit Uhrzeit und Kanal erfasst · AK-2: ≥ 90 % der Absagen mit Grund · AK-3: Nachfrage = angenommen + abgelehnt pro Stunde und Kanal berechenbar |
| **Abschlusskriterium**           | Proxy «angenommene Bestellungen» aus Abschnitt 2 der Data Gap Map neu geprüft                                                                                           |

*Begründung der Priorisierung: G-02 verzerrt die Nachfrage systematisch nach unten, und die Aushilfenplanung baut direkt darauf auf. G-01 (Telefon) und G-03 (Fertig-Zeit) folgen nach demselben Muster.*

# 2 Data-Sourcing-Canvas (Episode 15)

Pro Quellenkandidat ein Canvas. Felder 1 und 2 sind für alle Kandidaten gleich, weil sie aus der Lücke G-02 stammen. Der Canvas dokumentiert prüfbare Kandidaten, keine bereits bewilligte Beschaffung. Der Status der Quelle ist eine erste Einschätzung und wird in Kapitel 3 mit der Quellenbewertung bestätigt.

| **Canvas** | **Source-ID** | **Kandidat**                                          | **Beschaffungsform** | **Status der Quelle** |
|------------|---------------|-------------------------------------------------------|----------------------|-----------------------|
| **2.1**    | SRC-01        | Absage-Erfassung im Lokal (Bon/Strichliste)           | Collect              | geeignet              |
| **2.2**    | SRC-02        | Absagen aus den Partner-Portalen Just Eat / Uber Eats | Share                | bedingt geeignet      |
| **2.3**    | SRC-03        | Anrufprotokoll der Telefonanlage                      | Build                | nicht geeignet        |

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3"><strong>Data-Sourcing-Canvas · SRC-01: Absage-Erfassung im Lokal · Gap G-02</strong></td>
</tr>
<tr class="even">
<td><strong>1. Problem / Entscheidungsbedarf</strong></td>
<td><strong>2. Evidenzziel</strong></td>
<td><strong>3. Datenquelle (Kandidat)</strong></td>
</tr>
<tr class="odd">
<td><p>Gap / Bedarf: G-02</p>
<p>Nachfrage ist bei Absagen nicht direkt beobachtbar.</p>
<p>Entscheid: Aushilfen (Mittwoch) und Teigmenge (Vortag) für Fr/Sa (IR-01, IR-04).</p></td>
<td><p>Welche Evidenz benötigen wir?</p>
<p>Belastbare Zahl abgelehnter Bestellungen pro Stunde und Kanal, mit Grund, um die (nicht bediente) Nachfrage besser zu schätzen.</p>
<p>Akzeptanz: AK-1 bis AK-3</p></td>
<td><p>SRC-01</p>
<p>Datenhalter: Pizzeria Da Luigi</p>
<p>Methode: Beobachtung, manuelle Erfassung durch den Service</p>
<p>Zugang: Kürzel «A» + Grund auf dem Bon bzw. Strichliste am Telefon, wöchentlich in Excel</p></td>
</tr>
<tr class="even">
<td><strong>4. Evidenzbeitrag</strong></td>
<td><strong>5. Proxy-Annahme</strong></td>
<td><strong>6. Eignungstest (vor Beschaffung)</strong></td>
</tr>
<tr class="odd">
<td><p>Was liefert die Quelle?</p>
<p>Jede abgelehnte Bestellung vor Ort und am Telefon mit Uhrzeit, Kanal, Anzahl Pizzen und Grund.</p></td>
<td><p>Arbeitsannahme</p>
<p>Erfasste Absage = nicht bediente Nachfrage (Kunde bestellt nicht anderswo bei uns nach).</p></td>
<td><p>• Parallelzählung in 2 Spitzenstunden: Die Liste muss ≥ 95 % der von einer zweiten Person gezählten Absagen enthalten (wie AK-1)</p>
<p>• Probelauf an einem Samstag: Wie viele Einträge ohne Grund?</p></td>
</tr>
<tr class="even">
<td><strong>7. Merkmale der Quelle (erste Einschätzung)</strong></td>
<td><strong>8. Risiken und Einschränkungen</strong></td>
<td><strong>9. Offene Punkte / nächste Schritte</strong></td>
</tr>
<tr class="odd">
<td><p>Datenart: interne, selbst erhobene Daten</p>
<p>Granularität: pro Absage (Datum × Uhrzeit × Kanal)</p>
<p>Aktualität: sofort, Übertrag wöchentlich</p>
<p>Abdeckung: vor Ort und Telefon, Fr/Sa-Abend</p>
<p>Zeitbezug: ab Pilot, keine Historie</p></td>
<td><p>• Im Stress werden Einträge vergessen (Unterschätzung)</p>
<p>• Kunden, die gar nicht erst fragen, fehlen</p>
<p>• Grund ist subjektiv (Messung)</p></td>
<td><p>Kürzel und Gründe festlegen (Liste mit 4 Gründen)</p>
<p>Team am Donnerstag vor dem Pilot instruieren</p>
<p>Wer überträgt in Excel? → Datenverantwortliche</p>
<p>Reicht der Proxy für die Entscheidung?</p></td>
</tr>
<tr class="even">
<td colspan="2"><p><strong>Status der Quelle</strong></p>
<p><strong>☒ geeignet (prüfen / beschaffen) ☐ bedingt geeignet (mit Massnahmen) ☐ nicht geeignet (alternative Quelle suchen)</strong></p></td>
<td><p><strong>Nächster Schritt</strong></p>
<p><strong>Formular festlegen, Pilot 13./14.11. starten; in den Data Sourcing Plan überführen.</strong></p></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3"><strong>Data-Sourcing-Canvas · SRC-02: Absagen aus den Plattform-Portalen · Gap G-02</strong></td>
</tr>
<tr class="even">
<td><strong>1. Problem / Entscheidungsbedarf</strong></td>
<td><strong>2. Evidenzziel</strong></td>
<td><strong>3. Datenquelle (Kandidat)</strong></td>
</tr>
<tr class="odd">
<td><p>Gap / Bedarf: G-02</p>
<p>Nachfrage ist bei Absagen nicht direkt beobachtbar.</p>
<p>Entscheid: Aushilfen (Mittwoch) und Teigmenge (Vortag) für Fr/Sa (IR-01, IR-04).</p></td>
<td><p>Welche Evidenz benötigen wir?</p>
<p>Belastbare Zahl abgelehnter Bestellungen pro Stunde und Kanal, mit Grund, um die (nicht bediente) Nachfrage besser zu schätzen.</p>
<p>Akzeptanz: AK-1 bis AK-3</p></td>
<td><p>SRC-02</p>
<p>Datenhalter: Just Eat und Uber Eats (Kopie bei der Pizzeria)</p>
<p>Methode: Transaktionsaufzeichnung der Plattform</p>
<p>Zugang: Bestellbericht/Export im Partner-Portal gemäss Partnervertrag</p></td>
</tr>
<tr class="even">
<td><strong>4. Evidenzbeitrag</strong></td>
<td><strong>5. Proxy-Annahme</strong></td>
<td><strong>6. Eignungstest (vor Beschaffung)</strong></td>
</tr>
<tr class="odd">
<td><p>Was liefert die Quelle?</p>
<p>Abgelehnte und nicht angenommene App-Bestellungen mit Zeitstempel, Status und ggf. Grund.</p></td>
<td><p>Arbeitsannahme</p>
<p>Plattform-Absage = nicht bediente Nachfrage im App-Kanal.</p></td>
<td><p>• Testexport eines Wochenendes: Sind Zeit, Status, Grund enthalten?</p>
<p>• Abgleich mit der Anzahl Absagen auf dem Tablet</p>
<p>• Prüfen, ob Personendaten vor dem Export entfernt werden können</p></td>
</tr>
<tr class="even">
<td><strong>7. Merkmale der Quelle (erste Einschätzung)</strong></td>
<td><strong>8. Risiken und Einschränkungen</strong></td>
<td><strong>9. Offene Punkte / nächste Schritte</strong></td>
</tr>
<tr class="odd">
<td><p>Datenart: externe Plattformdaten (Share)</p>
<p>Granularität: pro Bestellung (Zeitstempel × Status)</p>
<p>Aktualität: täglich (zu prüfen)</p>
<p>Abdeckung: nur App-Kanäle</p>
<p>Zeitbezug: Historie im Portal (Dauer zu prüfen)</p></td>
<td><p>• Modus «ausgelastet» erzeugt gar keine Bestellung (Unterschätzung)</p>
<p>• Exportumfang und Felder unklar</p>
<p>• Abhängigkeit von Plattform und Vertrag</p>
<p>• Export enthält Name/Adresse</p></td>
<td><p>Historie: Wie weit zurück?</p>
<p>Zugriffsrecht: Erlaubt der Vertrag eigene Auswertungen?</p>
<p>Zeitauflösung: Minute oder nur Tag?</p>
<p>Protokoll, wann «ausgelastet» aktiv war</p></td>
</tr>
<tr class="even">
<td colspan="2"><p><strong>Status der Quelle</strong></p>
<p><strong>☐ geeignet (prüfen / beschaffen) ☒ bedingt geeignet (mit Massnahmen) ☐ nicht geeignet (alternative Quelle suchen)</strong></p></td>
<td><p><strong>Nächster Schritt</strong></p>
<p><strong>Testexport ziehen, Vertrag prüfen; mit Auflage «ohne Personendaten» in den Plan überführen.</strong></p></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3"><strong>Data-Sourcing-Canvas · SRC-03: Anrufprotokoll der Telefonanlage · Gap G-02</strong></td>
</tr>
<tr class="even">
<td><strong>1. Problem / Entscheidungsbedarf</strong></td>
<td><strong>2. Evidenzziel</strong></td>
<td><strong>3. Datenquelle (Kandidat)</strong></td>
</tr>
<tr class="odd">
<td><p>Gap / Bedarf: G-02</p>
<p>Nachfrage ist bei Absagen nicht direkt beobachtbar.</p>
<p>Entscheid: Aushilfen (Mittwoch) und Teigmenge (Vortag) für Fr/Sa (IR-01, IR-04).</p></td>
<td><p>Welche Evidenz benötigen wir?</p>
<p>Belastbare Zahl abgelehnter Bestellungen pro Stunde und Kanal, mit Grund, um die (nicht bediente) Nachfrage besser zu schätzen.</p>
<p>Akzeptanz: AK-1 bis AK-3</p></td>
<td><p>SRC-03</p>
<p>Datenhalter: Pizzeria (Telefonanlage)</p>
<p>Methode: Systemlog der Anlage</p>
<p>Zugang: Export der Anrufliste (eingegangen, verpasst)</p></td>
</tr>
<tr class="even">
<td><strong>4. Evidenzbeitrag</strong></td>
<td><strong>5. Proxy-Annahme</strong></td>
<td><strong>6. Eignungstest (vor Beschaffung)</strong></td>
</tr>
<tr class="odd">
<td><p>Was liefert die Quelle?</p>
<p>Verpasste Anrufe pro Stunde als Hinweis auf Kunden, die bei besetzter Leitung aufgeben.</p></td>
<td><p>Arbeitsannahme</p>
<p>Verpasster Anruf ≈ verlorene Bestellung.</p></td>
<td><p>• Testauszug: Zeitstempel ohne Telefonnummer möglich?</p>
<p>• Abgleich verpasster Anrufe mit SRC-01 in denselben Stunden</p></td>
</tr>
<tr class="even">
<td><strong>7. Merkmale der Quelle (erste Einschätzung)</strong></td>
<td><strong>8. Risiken und Einschränkungen</strong></td>
<td><strong>9. Offene Punkte / nächste Schritte</strong></td>
</tr>
<tr class="odd">
<td><p>Datenart: interner Systemlog</p>
<p>Granularität: pro Anruf</p>
<p>Aktualität: täglich</p>
<p>Abdeckung: nur Telefon</p>
<p>Zeitbezug: Speicherdauer der Anlage unklar</p></td>
<td><p>• Telefonnummer ist Personendatum</p>
<p>• Mehrfachanrufe derselben Person zählen doppelt (Überschätzung)</p>
<p>• Misst Anrufversuche, nicht Bestellungen</p>
<p>• Proxy schwach</p></td>
<td><p>Kann die Anlage Nummern ausblenden?</p>
<p>Aufbewahrung und Löschung klären</p>
<p>Nur sinnvoll als Zusatzindiz zu SRC-01</p></td>
</tr>
<tr class="even">
<td colspan="2"><p><strong>Status der Quelle</strong></p>
<p><strong>☐ geeignet (prüfen / beschaffen) ☐ bedingt geeignet (mit Massnahmen) ☒ nicht geeignet (alternative Quelle suchen)</strong></p></td>
<td><p><strong>Nächster Schritt</strong></p>
<p><strong>Zurückstellen; nur als Fallback-Indiz prüfen, sobald der Datenschutz geklärt ist.</strong></p></td>
</tr>
</tbody>
</table>

# 3 Data Sourcing Plan (Episode 16)

## 3.1 Kandidaten

| **Source-ID** | **Herkunft / Datenhalter**            | **Erhebungsmethode**            | **Zugangsweg**                     | **Beschaffungsweg**    | **Status der Quelle** |
|---------------|---------------------------------------|---------------------------------|------------------------------------|------------------------|-----------------------|
| **SRC-01**    | eigene Erhebung im Lokal              | Beobachtung, manuelle Erfassung | Papier/Bon, wöchentlich in Excel   | Collect                | geeignet              |
| **SRC-02**    | Lieferplattformen Just Eat, Uber Eats | Transaktionsaufzeichnung        | Dateiexport aus dem Partner-Portal | Share (Partnervertrag) | bedingt geeignet      |
| **SRC-03**    | Telefonanlage der Pizzeria            | Systemlog                       | Export der Anrufliste              | Build                  | nicht geeignet        |

## 3.2 Quellenbewertung

Bewertet wird in vier Stufen: Eignung zuerst, Optimierung danach. Ist ein Muss-Kriterium verletzt, scheidet die Quelle aus, egal wie gut sie sonst abschneidet; ist es ungeklärt, wird sie zurückgestellt. Skala für Stufe 2 und 3: + gut · ○ mittel · – schwach.

| **Kriterium**                           | **SRC-01 Absage-Erfassung**                             | **SRC-02 Plattform-Absagen**                                       | **SRC-03 Anrufprotokoll**                       |
|-----------------------------------------|---------------------------------------------------------|--------------------------------------------------------------------|-------------------------------------------------|
| **Rechtmässiger Zugang**                | ja: eigene Daten                                        | ja: Partner-Portal, Umfang zu prüfen                               | ja: eigene Anlage                               |
| **Zulässige Nutzung**                   | ja: keine Personendaten                                 | ja, mit Auflage: Export ohne Name und Adresse                      | ungeklärt: Telefonnummern                       |
| **Plausible Evidenz**                   | ja: direkte Beobachtung                                 | ja: direkte Systemdaten                                            | fraglich: nur Indiz                             |
| **Ergebnis Stufe 1**                    | erfüllt                                                 | erfüllt unter Auflage                                              | offen (Nutzung ungeklärt) → zurückgestellt      |
| **Relevanz für G-02**                   | \+ misst Absagen direkt                                 | \+ misst Absagen direkt                                            | – misst Anrufversuche                           |
| **Zeitbezug**                           | \+ Uhrzeit pro Absage, sofort                           | ○ Zeitstempel, Export täglich                                      | \+ Zeitstempel pro Anruf                        |
| **Messung**                             | ○ manuell, Grund subjektiv                              | \+ automatisch, einheitlich                                        | ○ automatisch, aber Mehrfachanrufe              |
| **Abdeckung**                           | ○ vor Ort und Telefon                                   | ○ nur App                                                          | – nur Telefon                                   |
| **Bias (siehe 3.3)**                    | ○ Unterschätzung im Stress                              | ○ Unterschätzung bei «ausgelastet»                                 | – Überschätzung durch Wiederholer               |
| **Kosten**                              | \+ keine                                                | \+ keine (im Vertrag enthalten)                                    | \+ keine                                        |
| **Aufwand**                             | ○ ca. 5 s pro Absage, Instruktion                       | \+ ca. 10 Min. pro Woche                                           | ○ Export einrichten, Datenschutz klären         |
| **Aktualisierung**                      | \+ laufend, wöchentlicher Übertrag                      | ○ täglich bis wöchentlich                                          | ○ täglich                                       |
| **Stabilität**                          | ○ abhängig von der Disziplin des Teams                  | ○ abhängig von Plattform-Änderungen                                | \+ stabil                                       |
| **Nachhaltigkeit**                      | \+ dauerhaft in den Ablauf integrierbar                 | \+ dauerhaft, solange der Vertrag läuft                            | – nicht weiterverfolgt                          |
| **Begründung**                          | deckt vor Ort und Telefon; einfach, keine Personendaten | deckt App-Kanäle; automatisch und vollständig für erfasste Absagen | Muss-Kriterium Nutzung ungeklärt, Proxy schwach |
| **Offene Tests**                        | Parallelzählung in 2 Spitzenstunden (≥ 95 %, AK-1)      | Testexport, Protokoll «ausgelastet»                                | –                                               |
| **Status der Quelle**                   | geeignet → beschaffen                                   | bedingt geeignet → mit Auflage beschaffen                          | nicht geeignet → Fallback-Indiz                 |
| **Stufe 1: Muss-Kriterien (ja / nein)** |                                                         |                                                                    |                                                 |
| **Stufe 2: Qualität und Validität**     |                                                         |                                                                    |                                                 |
| **Stufe 3: Betrieb**                    |                                                         |                                                                    |                                                 |
| **Stufe 4: Entscheid**                  |                                                         |                                                                    |                                                 |

*SRC-01 und SRC-02 sind komplementär statt austauschbar: Sie decken verschiedene Kanäle derselben Lücke ab. Die Einschätzungen sind begründete Annahmen, noch nicht empirisch geprüft.*

## 3.3 Bias-Audit

| **Prüffrage**                                 | **SRC-01**                                                                                                                 | **SRC-02**                                                                                                      | **SRC-03**                                                                   |
|-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| **1 Welche Zielgrösse bildet die Quelle ab?** | Absagen vor Ort und am Telefon                                                                                             | Absagen in der App                                                                                              | Anrufversuche                                                                |
| **2 Was fehlt systematisch?**                 | Kunden, die gar nicht erst fragen; Einträge in der hektischsten Viertelstunde                                              | Nachfrage, solange der Modus «ausgelastet» aktiv ist                                                            | Kunden, die online statt anrufen; Wiederholer zählen doppelt                 |
| **3 Welche Proxys, wann versagen sie?**       | Absage = verlorene Nachfrage; versagt, wenn der Kunde später doch bestellt                                                 | Plattform-Absage = verlorene Nachfrage; versagt bei Stornos durch Kunden                                        | Verpasster Anruf = verlorene Bestellung; versagt bei Mehrfachanrufen         |
| **4 In welche Richtung verzerrt?**            | eher Unterschätzung                                                                                                        | Unterschätzung (Modus «ausgelastet»)                                                                            | eher Überschätzung                                                           |
| **Bias-Art (Folie «Bias bei fremden Daten»)** | Selection Bias: Kunden, die gar nicht fragen, fehlen · zeitliche Selektion: Lücken genau in der hektischsten Viertelstunde | Selection Bias: Nachfrage im Modus «ausgelastet» fehlt · zeitliche Selektion: betrifft gerade die Spitzenzeiten | Measurement Bias: ein Anruf ist keine Bestellung; Wiederholer zählen doppelt |
| **5 Welche Prüfung erkennt den Bias?**        | Parallelzählung in 2 Spitzenstunden                                                                                        | Protokoll, wann «ausgelastet» aktiv war                                                                         | Abgleich mit SRC-01 in denselben Stunden                                     |

*Ungeprüft ist nicht gleich unverzerrt: Das Restrisiko (Kunden, die gar nicht erst fragen) bleibt dokumentiert.*

## 3.4 Datenschutz- und Ethik-Check

| **Prüfpunkt**                               | **SRC-01**                                                | **SRC-02**                                                                                                                  | **SRC-03**                                                              |
|---------------------------------------------|-----------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| **Zweck, Datenhalter, Berechtigung**        | Wochenendplanung · Pizzeria · GF und Datenverantwortliche | Wochenendplanung · Plattform, Kopie bei der Pizzeria · gemäss Partnervertrag                                                | Wochenendplanung · Pizzeria · GF                                        |
| **Lizenz und Weitergabe**                   | eigene Daten, keine Weitergabe                            | Nutzung gemäss Partner-AGB nur für die eigene Betriebsplanung; keine Weitergabe an Dritte (vor dem Pilot im Vertrag prüfen) | eigene Daten, keine Weitergabe                                          |
| **Personenbezug, Re-Identifikation**        | keiner: nur Zeit, Kanal, Anzahl, Grund                    | Name und Adresse beim Export entfernen                                                                                      | Telefonnummer ist Personendatum, muss ausgeblendet oder gelöscht werden |
| **Datensparsamkeit, Aufbewahrung, Schutz**  | nur nötige Felder; Ablage /rohdaten; 12 Monate            | nur Zeit, Status, Grund, Anzahl Pizzen                                                                                      | nur Zeitstempel und Status; Nummer nie speichern                        |
| **Repräsentativität, Ausschlüsse, Schäden** | Mitarbeitende werden nicht einzeln bewertet               | keine                                                                                                                       | Risiko der Kontaktaufnahme ohne Einwilligung                            |
| **Ergebnis**                                | freigegeben                                               | freigegeben unter Auflagen (Export ohne Personendaten)                                                                      | ungeklärt, zurückgestellt                                               |

*Rechtlicher Rahmen: Datenschutzgesetz (DSG). Die Checkliste ersetzt keine juristische Freigabe. Ungeklärte Rechte sind ein offener Entscheid, kein stillschweigendes Ja.*

## 3.5 Entscheid

| **Punkt**         | **Entscheid**                                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------------------------|
| **Gewählter Weg** | SRC-01 und SRC-02 kombiniert: vor Ort und Telefon über die Absage-Erfassung, App-Kanäle über die Plattform-Exporte |
| **Zuständigkeit** | SRC-01: Service · SRC-02: Geschäftsführer · Zusammenführung: Datenverantwortliche                                  |
| **Pilot**         | Freitag und Samstag, 13./14. und 20./21. November 2026, jeweils 17 bis 22 Uhr                                      |
| **Termin**        | Auswertung gegen AK-1 bis AK-3 am 23. November 2026                                                                |
| **Nicht gewählt** | SRC-03, weil der Proxy schwach ist und der Datenschutz ungeklärt                                                   |

*DWH-Bezug: SRC-01 und SRC-02 landen zuerst im Data Extraction Layer. Die Integration mit den Kassendaten folgt in Woche 9 (Data Engineering).*

## 3.6 Fallback

| **Falls …**                                               | **dann …**                                                                                                     |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| **die Plattform keinen Export liefert**                   | Absagen wöchentlich manuell aus dem Portal übertragen                                                          |
| **SRC-01 im Stress lückenhaft ist (AK-1 nicht erreicht)** | Wochenende als unvollständig markieren; zusätzlich SRC-03 als Indiz prüfen, sobald der Datenschutz geklärt ist |
| **beide Quellen nicht ausreichen**                        | Proxy einschränken: Nachfrage nur als Untergrenze ausweisen und die Prognose als Spanne angeben                |

# 4 Provenance Register

Das Register beschreibt den tatsächlich entstandenen Datenausschnitt. Referenzkette: G-02 → SRC-01, SRC-02 → DATA-01.

| **Bereich**        | **DATA-01 Absagen G-02**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Identifikation** | DATA-ID: DATA-01 · Gap-ID: G-02 · Source-IDs: SRC-01, SRC-02                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Ursprung**       | Tatsächlicher Ursprung: Python-Generator des Projektteams (gen_v2.py, liegt der Abgabe bei), Datenhalter: Projektteam, Ablage /rohdaten/simulation · Nachgebildete Quellen: SRC-01 (Absage-Erfassung im Lokal) und SRC-02 (Plattform-Exporte); aus ihnen stammt kein einziger echter Datensatz · Nutzungsrecht: frei, nur für Projektzwecke                                                                                                                                                                                                                                                                                                                                                                        |
| **Erzeugung**      | Synthetisch erzeugt am 11.11.2026 mit Python-Generator v2 (ersetzt v1 vom 5.11.) · Zeitraum: vier Abende (Fr 23.10., Sa 24.10., Fr 30.10., Sa 31.10.2026), 17 bis 22 Uhr · Parameter: Seed 20261111; 52 Zeilen; Basis-Absagen pro Stunde 17 h: 1, 18 h: 2, 19 h: 4, 20 h: 3, 21 h: 1 (rund 10 pro Abend wie im Mission Brief), je Stunde zufällig × 0,6 bis 1,4; Samstag × 1,2; Kanalanteile Telefon 45 %, Just Eat 30 %, Uber Eats 20 %, vor Ort 5 %; Pizzen pro Bestellung 1 bis 4; Wahrscheinlichkeit für fehlenden Grund bei SRC-01 8 % (realisiert: 4 von 18 = 22 %) · Im selben Lauf entsteht DATA-02 (angenommene Bestellungen pro Abend, Stunde und Kanalgruppe; höchstens 24 pro Stunde, App-Anteil 45 %) |
| **Bearbeitung**    | Keine Filterung; Zeitformat HH:MM; abgeleitet: stunde = Stunde aus uhrzeit, kanal_gruppe = Kasse (vor Ort, Telefon) bzw. App (Just Eat, Uber Eats); IDs nach Zeit sortiert vergeben; Spalten gap_id = G-02 und synthetisch = ja                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Grenzen**        | Synthetisch, keine empirische Evidenz · Kunden, die gar nicht erst fragen, fehlen · Nachfrage im Modus «ausgelastet» nicht abgebildet (es entstehen dort keine Bestellungen, also auch keine Absagen) · Proxy Absage = verlorene Nachfrage                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Verantwortlich** | Datenverantwortliche                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

*Datasheet-Perspektive: Der Datensatz entstand, um Format, Felder und Auswertung für G-02 vor dem Pilot zu testen. Geeignet für Pipeline-Tests in Woche 9, nicht geeignet als Beleg für das tatsächliche Absagevolumen.*

# 5 Erster nutzbarer Datenausschnitt (synthetisch)

Datei: DATA-01_Absagen_G-02_SYNTHETISCH_v2.csv · Granularität: eine Zeile pro abgelehnte Bestellung · Trennzeichen Semikolon. Begleitdatei für AK-3: DATA-02_Angenommene_Bestellungen_SYNTHETISCH_v2.csv mit 40 Zeilen, eine pro Abend, Stunde und Kanalgruppe (Felder: datum, wochentag, stunde, kanal_gruppe, bestellungen_angenommen, pizzen, synthetisch). Der Kassen-Ausschnitt aus Woche 7 (Sa/So) ist nicht Teil dieser Abgabe.

| **Feld**             | **Typ**     | **Bedeutung**                                                                                                                    | **Quelle**     |
|----------------------|-------------|----------------------------------------------------------------------------------------------------------------------------------|----------------|
| **absage_id**        | Text        | eindeutige ID (DATA-01-001 …)                                                                                                    | generiert      |
| **datum, wochentag** | Datum, Text | Tag der Absage (Fr, Sa)                                                                                                          | SRC-01, SRC-02 |
| **uhrzeit**          | HH:MM       | Zeitpunkt der Absage                                                                                                             | SRC-01, SRC-02 |
| **stunde**           | Zahl 17–21  | aus uhrzeit abgeleitet; Join-Schlüssel für AK-3                                                                                  | abgeleitet     |
| **kanal**            | Text        | vor Ort, Telefon, Just Eat, Uber Eats                                                                                            | SRC-01, SRC-02 |
| **kanal_gruppe**     | Text        | Kasse (vor Ort, Telefon) oder App (Just Eat, Uber Eats); gleiche Werte wie in DATA-02                                            | abgeleitet     |
| **source_id**        | Text        | SRC-01 oder SRC-02                                                                                                               | Provenance     |
| **gap_id**           | Text        | G-02                                                                                                                             | Provenance     |
| **anzahl_pizzen**    | Zahl        | Pizzen der abgelehnten Bestellung                                                                                                | SRC-01, SRC-02 |
| **grund**            | Text        | SRC-01: keine Kapazität, Wartezeit zu lang, kein Teig · SRC-02: keine Kapazität, Wartezeit zu lang, nicht rechtzeitig angenommen | SRC-01, SRC-02 |
| **synthetisch**      | ja/nein     | Kennzeichnung synthetischer Daten                                                                                                | Provenance     |

| **Profiling-Befund**         | **Nenner**                        | **Anteil**  |
|------------------------------|-----------------------------------|-------------|
| **Zeilen**                   | 52 Absagen (18 SRC-01, 34 SRC-02) | 100 %       |
| **uhrzeit gefüllt**          | 52 von 52                         | 100 %       |
| **kanal gefüllt**            | 52 von 52                         | 100 %       |
| **grund gefüllt (SRC-01)**   | 14 von 18                         | 78 %        |
| **grund gefüllt (SRC-02)**   | 34 von 34                         | 100 %       |
| **doppelte absage_id**       | 0 von 52                          | 0 %         |
| **kanal_gruppe Kasse / App** | 18 / 34 von 52                    | 35 % / 65 % |
| **Absagen um 19 Uhr**        | 16 von 52                         | 31 %        |

*Profiling-Befunde sind noch keine Eignungsbewertung. Die Zahlen beschreiben den synthetischen Ausschnitt, nicht den Betrieb.*

# 6 Prüfung gegen die Akzeptanzkriterien und Gap-Status

| **Kriterium**                                          | **Technischer Test (Schema)**                                                                                                                                                                                                                  | **Fachlicher Evidenztest**              | **Evidenzstatus** |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|-------------------|
| **AK-1 ≥ 95 % der Absagen mit Uhrzeit und Kanal**      | erfüllt: 52 von 52                                                                                                                                                                                                                             | erst im Pilot messbar (Parallelzählung) | ungeprüft         |
| **AK-2 ≥ 90 % der Absagen mit Grund**                  | gesamt erfüllt: 48 von 52 (92 %); SRC-01 allein nicht erfüllt: 14 von 18 (78 %)                                                                                                                                                                | erst im Pilot messbar                   | ungeprüft         |
| **AK-3 Nachfrage = angenommen + abgelehnt pro Stunde** | erfüllt: Join über datum + stunde + kanal_gruppe mit DATA-02 läuft; Nachfrage für 40 von 40 Zeilen berechnet (394 angenommen + 52 abgelehnt = 446). Die Kassendaten aus Woche 7 haben andere Schlüsselwerte und werden in Woche 9 harmonisiert | echte Daten fehlen                      | ungeprüft         |

**Gap-Status G-02: ungeprüft. Der Datenausschnitt ist technisch nutzbar, schliesst die Evidenzlücke aber nicht, weil er synthetisch ist. Als erfüllt gilt G-02 erst, wenn der Pilot AK-1 bis AK-3 mit echten Daten erfüllt. Der technische Test zeigt schon, worauf im Pilot zu achten ist: Bei der manuellen Erfassung (SRC-01) fehlt der Grund zu oft.**

*Beschaffungserfolg und Schliessung der Evidenzlücke sind zwei verschiedene Prüfungen.*

# Anhang: Übersicht der übrigen Lücken

| **Gap**  | **Lücke**                       | **Quelle (Kurzform)**                          | **Status**               |
|----------|---------------------------------|------------------------------------------------|--------------------------|
| **G-01** | Telefonbestellungen fehlen      | Kürzel «T» auf dem Bon, Übertrag in die Kasse  | nächster Sourcing-Zyklus |
| **G-03** | Fertig-Zeit fehlt               | «Fertig»-Taste in der Kasse, ohne Login        | nächster Sourcing-Zyklus |
| **G-04** | Kein Teigprotokoll              | Formular in der Küche                          | nächster Sourcing-Zyklus |
| **G-05** | Wetterprognose nicht archiviert | MeteoSchweiz; Prognose am Mi notieren          | nächster Sourcing-Zyklus |
| **G-06** | Doppelerfassung Kasse/App       | Abgleich über Bestellnummer                    | Woche 9 (Pipeline)       |
| **G-07** | Ist-Besetzung                   | Zeile auf der Strichliste: Personen pro Stunde | nächster Sourcing-Zyklus |
| **G-08** | Küchenkapazität                 | aus G-03 und G-07 berechnet                    | nach G-03 und G-07       |
| **G-09** | Reaktion auf Wartezeit          | Plattform fragen, sonst Feldexperiment         | später                   |
| **G-10** | Bewertungen                     | nur als Indiz (einschränken)                   | laufend                  |
| **G-11** | Gründe bei Sonne                | qualitativ erfragen (verzichten auf Daten)     | später                   |
