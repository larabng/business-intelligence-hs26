# Business Intelligence (HS2026) – ZHAW

Repository für das Modul **Business Intelligence** (w.BA.XX.3BI-WIN.XX, 6 ECTS, Deutsch) im HS2026 und das Semesterprojekt **Pizzeria Da Luigi**.

## Eckdaten

| | |
| --- | --- |
| Modulverantwortung | Christian Hitz, Mario Gellrich (Stellvertretung) |
| Dozierende | Christian Hitz, Václav Pechtor |
| Grossklasse (VZ) | Montag 12:00–13:45, SW 224 |
| Kleinklasse (VZ) | Mittwoch 10:00–11:45, MU O2.040 (BIS24a & BIS24b) |
| Pflichtliteratur | Cao, L. – *Data Science Thinking* (ISBN 978-3-319-95092-1, gratis via ZHAW-Bibliothek) |
| Unterlagen | ausschliesslich auf Moodle (Semesterprogramm kann ändern) |

## Leistungsnachweis

- **Prüfungszulassung:** 3 von 3 Kleinklassen-Testaten bestanden (Pass/Fail, 5er-Gruppen, Team Contributions zählen individuell – keine Punkte für Trittbrettfahrer). Genaue Zuordnung Woche ↔ Testat: in der KK / auf Moodle bestätigen.
- **Modulendprüfung:** 100 % der Note, schriftlich, 90 Min.
  - 30 Min. Single Choice (4 Optionen)
  - 60 Min. Case Study (Anwendung der KK-Artefakte)
  - Geprüft: GK-Theorie, KK-Artefakte, Selbststudium
  - Hilfsmittel: kein Taschenrechner, Wörterbuch erlaubt
- Keine Nachbesserung von Leistungsnachweisen möglich.

## Semesterprojekt – Pizzeria Da Luigi

Roter Faden ist das **10-Fragen-Modell** (System-to-Decision Framework): Das gewählte sozio-technische System wird über 14 Wochen weiterentwickelt – CLD → Fragen/Requirements → Daten → Pipeline → Automation/Governance → Decision Interface → integriertes BI-Konzept + Abschlusspräsentation.

**Team:** Michele (Projektleitung) · Darren (Domäne) · Daniele (Daten) · Leandro & Lara (Kommunikation)

## Struktur

**Für weitere Aufgaben zuerst [`PIZZERIA_DA_LUIGI.md`](PIZZERIA_DA_LUIGI.md) lesen** – kompletter Projektkontext (System, Entscheidungen, Modelle, Gaps, Star Schema, nächste Schritte).

```
PIZZERIA_DA_LUIGI.md        Projektkontext auf einen Blick
docs/
  kursplan.md               Modulbeschreibung, Ort/Zeit, Benotung, Prüfung
  wochenuebersicht.md       Woche 1–14: Ziele, GK-Episoden, KK-Aufgaben, Deliverables
  aufgabenverteilung.md     Rollen & Aufgaben pro Woche im Team
projekt/
  deliverables.md           Status aller Deliverables mit Dateiverweisen
  woche01-system-charter/   System Charter V2, Projektjournal (+ ältere Versionen)
  woche02-05-modelle/       Kontextdiagramm v8, CLD final, Stock-Flow v8.1 (Vensim .mdl)
  woche05-mission-brief/    Antwortkarten, BI Mission Brief V2, KK-Präsentationen
  woche06-requirements/     IR Canvas, IR-Katalog, Traceability, Data Product Canvas
  woche07-target-analysis/  Clark-Analyse, Canvas, Traceability, Data Gaps
  woche08-data-sourcing/    Data Gap Map, Data Sourcing Plan G-02, Provenance, Präsentation
  woche09-star-schema/      Star Schema, technische Doku, Spickzettel
  daten/                    synthetischer Datenausschnitt (CSV)
  uebungen/                 Übungsmodelle aus der KK
notizen/                    BI-Zusammenfassung Woche 1–8 (Prüfungsvorbereitung)
```

Jede .docx/.pptx/.pdf hat daneben eine gleichnamige **.md-Textversion**, damit der Inhalt direkt auf GitHub (und für Claude) lesbar ist. Vensim-Modelle (.mdl) mit Vensim PLE öffnen.

Code der Pipeline (BigQuery): separates Repo `larabng/daeng-hs26-gcp-banlar01`.

## Quellen

Semesterprogramm v4.3, Modulbeschreibung (gültig ab HS2026), Einführungsfolien Woche 1, Team-Absprache (Notion: Studienplaner › Kurse › Business Intelligence).
