# Pizzeria Da Luigi – Projektkontext (Stand Woche 9)

Lies diese Datei zuerst: Sie enthält alles Wichtige zum Semesterprojekt, damit die nächsten Aufgaben (Woche 10–14) darauf aufbauen können. Details stehen in den Abgaben unter `projekt/`. Jede Word-, PowerPoint- und PDF-Datei liegt dort auch als lesbares `.md`.

> Fiktiver Fall. Alle Daten sind synthetisch, und viele Zahlen sind Teamschätzungen. Sie sind als Annahmen markiert.

## 1. Das System (System Charter V2, 15.10.2026)

- Ein Familienbetrieb seit über 20 Jahren: Pizza und Pasta vor Ort, zur Abholung und per Lieferung. Ein Standort mit ca. 30 Sitzplätzen und **ca. 400 Bestellungen pro Woche**.
- **Lieferzusage 45 Min.**, davon ca. 10 Min. Lieferweg → **die Küche hat 35 Min.**
- Zweck: authentische Küche, gemütliche Atmosphäre für die Nachbarschaft, wirtschaftlicher Erhalt des Familienbetriebs.
- Personal: Cousin A (Geschäftsführung), Cousin B (Küchenchef), zwei Freunde (Service), 2–3 Studierende als Aushilfen am Wochenende.
- **Innerhalb der Systemgrenze:** Küche und Ofen, Bestellannahme (Telefon, vor Ort, Lieferplattform), Einkauf (2× pro Woche), Personaleinsatzplanung, Service und Lieferung, Kassensystem als Datenquelle, Preise, Aktionen, lokale Vermarktung.
- **Ausserhalb:** externe Lieferplattform, Lokal, Buchhaltung, Reinigungskraft.
- Priorität bei der Bestellannahme: zuerst vor Ort, dann App, dann Telefon.

### Drei wiederkehrende Entscheidungen (der Kern des ganzen Projekts)

| ID | Entscheidung | Wer | Wann | Grundlage heute |
| --- | --- | --- | --- | --- |
| D-01 | Bestellannahme bzw. Bestellstopp bei hoher Auslastung | Küchenchef | mehrmals pro Woche, v. a. Fr/Sa | Bauchgefühl, kein Limit → gelegentlich verspätete Lieferungen |
| D-02 | Wochenend-Einsatzplan (Fr/Sa) | Freunde (Service) | wöchentlich, am Mittwoch | WhatsApp-Absprache |
| D-03 | Teigmenge und Zutaten | Küchenchef | täglich, am Vortag | Erfahrung, Blick auf die Vorwoche |

**Kernproblem:** Die Wochenendnachfrage ist nicht planbar. Das führt zu Stau in der Küche, verspäteten Lieferungen, schlechten Bewertungen und am Ende zu Kundenverlust. Teig muss im Voraus gemacht werden, ohne dass man die Nachfrage kennt.

## 2. Modelle (Woche 2–5) → `projekt/woche02-05-modelle/`

- **Kontextdiagramm v8** (`Kontextdiagramm_Pizzeria_Da_Luigi_v8.jpg`): im Modell sind Kundschaft, Lieferplattform, Küchenpersonal mit Aushilfen und Konkurrenz (über die Kundschaft). Bewusst draussen sind Lieferanten, Buchhaltung, Reinigung und Behörden.
- **Ashby:** Die Bestellannahme nach Bauchgefühl ist eine Varietätslücke. Die Situation (schwankende Nachfrage und Kapazität) hat mehr Varietät als der Regler (eine Person ohne Schwelle).
- **VSM (Beer):** S1 Küche, Annahme, Service · S2 WhatsApp (schwach) · S3 die Cousins · S3* Audit fehlt · S4 Preise und Marketing (informell) · S5 Identität „authentische Küche, Familienbetrieb“.
- **CLD final** (`pizzeria_da_luigi_cld_finished.mdl`, Vensim):
  - **R1 Stress-Spirale:** Auslastung → Fehler und Nacharbeit → noch mehr Auslastung
  - **R2 Teigvorrat:** Bestellungen → Teigmenge → weniger Ausverkauf
  - **B1 Bestellstopp:** Auslastung → Ablehnungen → weniger angenommene Bestellungen (die einzige kurzfristige Bremse, sie wirkt erst, wenn der Stau schon da ist)
  - **B2 Ruf und Nachfrage:** Lieferzeit → Bewertung → Online-Nachfrage (verzögert)
  - **B3 Personalplanung:** Auslastung → Personal (verzögert, Plan nur wöchentlich)
  - **Feedforward:** Wochenende, Wetter, Events und Reservationen sind vorab bekannt, fliessen aber heute nicht in die Planung ein.
- **Stock-Flow v8.1** (`pizzeria_da_luigi_sfd_v8.mdl`, vereinfacht: `..._sfd_einfach.mdl`): Teamschätzung von 9 Bestellungen pro Stunde als Basis und **28 pro Stunde in der Spitze (18–21 Uhr)**, bei einer Kapazität von 2 Personen ≈ **24 pro Stunde**. Durchlaufzeit im Normalbetrieb ca. 20 Min.
  - Simulation Freitag 17–23 Uhr: **ohne Stopp** steigt die Durchlaufzeit auf 49 Min. (ab 19:38 über 35 Min.) · **mit Regel** höchstens 24 Min., aber 10 von 111 Bestellungen verloren · **Aushilfe nach Prognose** 20 Min., keine Verluste (bei perfekter Prognose).

## 3. Mission Brief und Antwortkarten (Woche 4–5) → `projekt/woche05-mission-brief/`

- **Antwortkarten** (Decision Context Cards), aktuell ist `Pizzeria_Da_Luigi_KKW5.pptx`. Die ältere Datei `Antwortkarten_...docx` ist überholt.
  - Karte 1: Bestellstopp-Regel nach offenen Bons. 1–3 offen: Normalbetrieb · 4–7 offen: Liefer-App pausieren · ab 8 offen: auch das Telefon stoppen.
  - Karte 2 (Feedforward): Aushilfen nach einer Nachfrageprognose aus Kassendaten, Wetter, Kalender und Events, Reservationen und Plattform-Aktionen.
  - Karte 3: Teigmenge.
- **BI Mission Brief V2** (22.10.2026), an den Küchenchef gerichtet: Strichliste über 4 Wochenenden (23.10.–14.11.). Der Service notiert bei jeder Lieferannahme die offenen Bestellungen, die Abgangszeit, App-Pausen, Regen, Anlässe und Reservationen. Die Grenze liegt bei **5 % verspäteten Lieferungen**. Keine Anschaffung, ca. 10 Min. pro Abend.
  - H1: Ein Stopp ab mehr als 3 offenen Bons senkt die Verspätungen (B1).
  - H2: Aushilfen nach Prognose verhindern die Schlange von 18–21 Uhr (Feedforward).
  - H3: Nebenwirkung: Häufigere Pausen treiben Gäste zur Konkurrenz.
  - Kennzahlen pro Bestellung (Verspätungsquote, Ablehnungsquote bei vergleichbarer Nachfrage), **keine Kundenbewertung** (verzerrt und verzögert).

## 4. Requirements (Woche 6) → `projekt/woche06-requirements/`

- Information Requirements Canvas für D-01, D-02 und D-03 · Katalog **IR-01 bis IR-05** · Akzeptanzkriterien im Format GEGEBEN–WENN–DANN · Traceability Matrix · Data Product Canvas („Auslastungsampel“).

## 5. Target-Centric Analysis und Data Gaps (Woche 7–8)

- `woche07-target-analysis/abgabewoche7`: Clark-Diagramm (Ziel: Wochenendnachfrage gegenüber Kapazität), IR Canvas, Traceability Matrix mit System Purpose S-03 (späte Lieferung → Bewertung → Kundenverlust), Data Product Canvas „Wochenend-Kapazitätsplaner“, Data-Gap-Tabelle.
- **Data Gap Map** (`woche08-data-sourcing/abgabewoche8_DataGapMap`):

| Gap | Beschreibung |
| --- | --- |
| G-01 | Telefonbestellungen fehlen in der Kasse |
| **G-02** | **Abgelehnte Bestellungen sind unsichtbar (priorisiert)** |
| G-03 | Fertig-Zeit fehlt |
| G-04 | Kein Teigprotokoll |
| G-05 | Wetterprognose nicht archiviert, Wetter und Events nicht verknüpft |
| G-06 | Mögliche Doppelerfassung Kasse/App |
| G-07 | Ist-Besetzung weicht vom Schichtplan ab |
| G-08 | Küchenkapazität unbekannt (in Pizzen pro Stunde messen, der Ofen ist der Engpass) |
| G-09 | Reaktion der Kundschaft auf Wartezeit unbekannt |
| G-10 | Bewertungen sind nur ein schwacher Proxy |
| G-11 | Warum bei gutem Wetter weniger bestellt wird |

- **Data Sourcing Plan und Provenance Register zu G-02** (`Abgabe_Woche8_..._G02_final`): Quellen SRC-01 Kasse, SRC-02 Plattform-Export, SRC-03 Anrufprotokoll, Monitoring des Plattformstatus „ausgelastet“, Bias-Audit, Datenschutz-Check pro Quelle („mit Auflage“). Dazu die Präsentation `Praesentation_final` und der Spickzettel.
- Datenausschnitt (synthetisch): `projekt/daten/Datenausschnitt_Pizzeria_Da_Luigi_SIMULIERT.csv`. Werte pro Datum × Stunde × Kanal: 1 294 angenommene Bestellungen, 2 718 Pizzen, 9 App-Stornos, 4 Regentage.

## 6. Data Product MVP (Woche 9) → `projekt/woche09-star-schema/`

- **Star Schema** (BCNF): Fakt `fakt_bestellung_stunde`, Grain Datum × Stunde × Kanal × Status, FKs auf `dim_datum` (inkl. Wetter und Event), `dim_stunde`, `dim_kanal` und `dim_bestellstatus`. Kennzahlen: `anzahl_bestellungen`, `anzahl_pizzen` (NULL bei Absagen), `summe_durchlaufzeit_min` (vorerst NULL). Die Faktentabelle hat 432 Zeilen.
- Angenommene und abgelehnte Bestellungen stehen in derselben Faktentabelle. Damit ist G-02 im Modell abgebildet.
- Geschäftsregel: Ein leeres Storno-Feld in der Kasse bedeutet „unbekannt“, nicht 0. Eine 0 bei der App bedeutet „bekannt, kein Storno“.
- **Umsetzung:** ELT in Google Cloud. Projekt `daeng-banlar01-x4q9`, Region `europe-west6`, Bucket `gs://daeng-banlar01-x4q9-raw/pizzeria/`, BigQuery-Dataset `pizzeria_dwh`. SQL liegt im Repo **`larabng/daeng-hs26-gcp-banlar01`**, Ordner `sql/pizzeria_star_schema/` (01_ddl, 02_dimensionen, 03_elt, 04_checks). Alle 9 Tests sind bestanden.
- Bekannte Grenzen: synthetische Daten, fehlende Kassen-Stornos, Zeitfenster des Ausschnitts ≠ Projektscope Fr/Sa 17–22 Uhr.

## 7. Wie es weitergeht

| Woche | Thema | Deliverable | Anknüpfung |
| --- | --- | --- | --- |
| 10 | Automation & agentische Systeme | Automation Decision, Agent-/Workflow-Konzept, Mini-Prototyp | Bestellstopp-Regel (Karte 1) und Aushilfen-Prognose (Karte 2) auf der Automation Ladder einordnen; Prototyp auf `pizzeria_dwh` |
| 11 | Operations & Governance | Operating Model, RACI, Zugriffs- und Datenschutzkonzept, Failure Mode Review | Rollen: Cousins, Service, Aushilfen; Quellen SRC-01 bis SRC-03 |
| 12 | Storytelling & Decision Interface | getestetes Decision Interface | „Auslastungsampel“ bzw. „Wochenend-Kapazitätsplaner“ für Küchenchef und Service |
| 13 | Integration & Impact | integriertes BI-Konzept, Impact Plan, Roadmap | Traceability von System Charter bis Wirkung; H1–H3 |
| 14 | Abschluss | Präsentation, One-Pager, individuelle Reflexion | – |

## Team und Rollen

Michele (Projektleitung, GitHub: maniamic) · Darren (Domäne, GitHub: sgDarren) · Daniele (Daten) · Leandro & Lara (Kommunikation). Details: `docs/aufgabenverteilung.md`.
