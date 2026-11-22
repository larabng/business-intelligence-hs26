# Spickzettel_Star_Schema_Pizzeria_Da_Luigi

```
Spickzettel – Star Schema & Pipeline Pizzeria Da Luigi




Spickzettel – Star Schema & Pipeline Pizzeria
Da Luigi
  ​Nov 18, 2026        ·   ​@Lara Bangerter




In 30 Sekunden
Wir haben die Bestelldaten der Pizzeria in ein Star Schema gebracht und in Google Cloud
(BigQuery) umgesetzt. Damit kann die Pizzeria zwei Fragen beantworten: Wie viele
Aushilfen braucht es am Wochenende (Entscheid am Mittwoch), und wie viel Teig
(Entscheid am Vortag)?

Der Kern: Angenommene und abgelehnte Bestellungen stehen in derselben Tabelle. So
sieht man die echte Nachfrage und nicht nur das, was die Kasse gezählt hat. Das schliesst
die Lücke G-02 aus Woche 8.

Arbeitsteilung: Im Chat mit Claude haben wir das Modell entworfen und jeden Schritt
geprüft. Claude Code hat die Befehle in Google Cloud ausgeführt, jeden erst nach
Freigabe.


Begriffe einfach erklärt

   Begriff                                    Einfach gesagt                 Bei uns

   Star Schema                                Datenmodell für                1 Faktentabelle, 4 Dimensionen
                                              Auswertungen: eine
                                              Faktentabelle in der Mitte,
                                              Dimensionen darum herum
                                              wie ein Stern

   Faktentabelle                              Enthält die Zahlen, die man    fakt_bestellung_stunde:
                                              zählt oder summiert            Bestellungen, Pizzen,
                                              (Kennzahlen), plus je einen    Durchlaufzeit
                                              Fremdschlüssel pro
                                              Dimension

   Dimension                                  Beschreibt die Zahlen: wann,   Datum, Stunde, Kanal,
                                              wo, wie                        Bestellstatus

   Kennzahl (Fakt,                            Die Zahl selbst                anzahl_bestellungen,
   Measure)                                                                  anzahl_pizzen




                                                                                                         Page 1 of 6
Spickzettel – Star Schema & Pipeline Pizzeria Da Luigi




   Begriff                                    Einfach gesagt                  Bei uns

   Grain                                      Wofür eine Zeile in der         Datum × Stunde × Kanal × Status
                                              Faktentabelle steht

   PK / FK                                    Primärschlüssel macht eine      Fakten: 4 FKs, zusammen der
                                              Zeile eindeutig;                Schlüssel
                                              Fremdschlüssel verweist auf
                                              eine andere Tabelle

   BCNF (Boyce-Codd-                          Jede Spalte hängt nur vom       Wetter hängt nur am Datum →
   Normalform)                                ganzen Schlüssel ab, keine      steht in Dim_Datum, nicht in den
                                              versteckten Abhängigkeiten      Fakten

   Denormalisiert                             Absichtlich redundant, damit    Kanal und Kanalgruppe in
                                              Abfragen schnell und einfach    derselben Dimension
                                              sind

   ETL / ELT                                  Extract, Transform, Load. Bei   ELT: CSV roh laden, dann per SQL
                                              ELT wird zuerst geladen, dann   in BigQuery
                                              im Zielsystem umgebaut

   Staging                                    Zwischentabelle mit den         stg_datenausschnitt, alles als Text
                                              Rohdaten, unverändert

   Bucket                                     Ablage für Dateien in Google    daeng-banlar01-x4q9-raw
                                              Cloud Storage

   BigQuery / Dataset                         Das Data Warehouse von          pizzeria_dwh
                                              Google; ein Dataset ist ein
                                              Ordner für Tabellen

   Lineage                                    Datenherkunft: aus welchen      Tab «Lineage» in BigQuery
                                              Tabellen eine Tabelle befüllt
                                              wurde

   Roll-up / Drill-down                       Zusammenfassen (Stunde →        Nachfrage pro Tag und
                                              Tag) bzw. ins Detail gehen      Kanalgruppe
                                              (Tag → Stunde)

   Slice / Dice                               Einen Ausschnitt wählen (nur    Bestellungen pro Stunde an
                                              Regentage) bzw. mehrere         Regentagen
                                              Filter kombinieren

   NOT ENFORCED                               BigQuery speichert PK/FK,       Tests 2 und 3
                                              prüft sie aber nicht. Deshalb
                                              prüfen wir sie mit Tests




                                                                                                            Page 2 of 6
Spickzettel – Star Schema & Pipeline Pizzeria Da Luigi




Folie für Folie

   Folie                                       Kernaussage                     Das sagen wir

   1 Titel                                     Vom Rohdatum zum Star           «Wir zeigen, wie wir die
                                               Schema                          Bestelldaten der Pizzeria in ein Star
                                                                               Schema gebracht und in Google
                                                                               Cloud umgesetzt haben.»

   2 Ausgangslage                              Die Pizzeria plant ohne die     Aushilfen am Mittwoch, Teig am
                                               echte Nachfrage                 Vortag. Die Kasse zählt nur
                                                                               angenommene Bestellungen,
                                                                               abgelehnte fehlen. Darum wird die
                                                                               Nachfrage gerade in den
                                                                               Spitzenstunden unterschätzt.

   3 Star Schema                               Faktentabelle in der Mitte, 4   Eine Zeile = Datum × Stunde ×
                                               Dimensionen                     Kanal × Status. Die Faktentabelle
                                                                               hat nur Fremdschlüssel und Zahlen
                                                                               und ist in BCNF. Wetter und Event
                                                                               hängen nur vom Datum ab, darum
                                                                               stehen sie in dim_datum. Die
                                                                               Dimensionen sind bewusst
                                                                               redundant.

   4 Was das Schema                            Jede Tabelle beantwortet        Fakten = wie viel. Datum = wann
   zeigt                                       eine Frage                      und bei welchem Wetter. Stunde =
                                                                               um welche Zeit. Kanal = über
                                                                               welchen Weg. Status =
                                                                               angenommen oder abgelehnt.
                                                                               Nachfrage = angenommen +
                                                                               abgelehnt.

   5 Zielarchitektur und                       Vier Stationen, ELT             CSV → Cloud Storage (Extract) →
   Pipeline                                                                    BigQuery Staging (Load) → Star
                                                                               Schema per SQL (Transform).
                                                                               Regel: Leer heisst unbekannt, nicht
                                                                               0 (Kasse-Absagen).
                                                                               Fehlerbehandlung: BigQuery
                                                                               erkannte die Datentypen selbst,
                                                                               gelöst mit fester Spaltenliste; der
                                                                               Lauf ist wiederholbar. Region
                                                                               Zürich, Befehle von Claude Code
                                                                               nach unserer Freigabe.




                                                                                                               Page 3 of 6
Spickzettel – Star Schema & Pipeline Pizzeria Da Luigi




   Folie                                       Kernaussage                        Das sagen wir

   6 Google Cloud                              Was man in BigQuery sieht          Dataset pizzeria_dwh. Live:
                                                                                  Faktentabelle öffnen, Tab
                                                                                  «Schema» zeigt PK und FK, Tab
                                                                                  «Vorschau» die Daten.

   7 Tests                                     9 von 9 bestanden                  Keine Bestellung fehlt, keine Zeile
                                                                                  doppelt, jede Zeile passt zu ihren
                                                                                  Dimensionen, 432 Zeilen wie
                                                                                  erwartet. Wetter und Event gelten
                                                                                  pro Tag, das bestätigt das Modell.

   8 Ergebnis                                  Am Abend braucht es die            Abfrage aus BigQuery:
                                               Aushilfen                          angenommene Bestellungen pro
                                                                                  Stunde. Spitze 18 bis 20 Uhr mit 668
                                                                                  von 1 294 Bestellungen (gut die
                                                                                  Hälfte), Maximum 19 Uhr mit 259.
                                                                                  Kleinerer Peak am Mittag (12 Uhr:
                                                                                  139). Mit den Absagen wäre die
                                                                                  Abendspitze noch höher.

   9 Fazit                                     Erreicht, Grenzen, nächster        Daten an einem Ort, Nachfrage
                                               Schritt                            sichtbar. Grenzen: Daten simuliert,
                                                                                  Kasse-Absagen fehlen noch.
                                                                                  Nächster Schritt: Pilotdaten laden,
                                                                                  das Modell bleibt gleich.




Zahlen zum Merken

   Was                                                       Zahl

   Zeilen im Datenausschnitt (Staging)                       288

   Tage im Datenausschnitt                                   12 (Sa/So, 19.9. bis 25.10.2026)

   Stunden                                                   12 (11 bis 22 Uhr)

   Kanäle in Dim_Kanal                                       6 (4 vorbereitet für Pilotdaten, 2 Sammelzeilen
                                                             Kasse/App)

   Status in Dim_Bestellstatus                               5 (1 angenommen, 4 Absagegründe)

   Zeilen in der Faktentabelle                               432 = 144 Kasse + 144 App + 144 App-Absagen

   Angenommene Bestellungen                                  1 294




                                                                                                                  Page 4 of 6
Spickzettel – Star Schema & Pipeline Pizzeria Da Luigi




   Was                                                   Zahl

   Pizzen                                                2 718

   App-Absagen                                           9

   Regentage                                             4

   Tests                                                 9 von 9 bestanden

   Google-Cloud-Projekt                                  daeng-banlar01-x4q9, Region europe-west6
                                                         (Zürich)




Mögliche Fragen und Antworten
Warum ein Star Schema und kein normalisiertes Modell? Für Auswertungen braucht man
schnelle, einfache Abfragen. Jede Frage braucht nur einen Join von den Fakten zu den
nötigen Dimensionen. Die Redundanz in den Dimensionen nimmt man dafür in Kauf (Folie
«Star Schema», Woche 9).

Was ist der Primärschlüssel der Faktentabelle? Die Kombination der vier
Fremdschlüssel: datum_id, stunde_id, kanal_id, status_id. Auf dem Diagramm stehen nur
FKs, wie auf der Vorlesungsfolie.

Warum ist die Faktentabelle in BCNF? Die Kennzahlen hängen nur vom ganzen Schlüssel
ab. Alles, was nur von einem Teil abhängt (Wetter vom Datum), steht in einer Dimension.

Warum steht das Wetter nicht in der Faktentabelle? Wetter hängt nur vom Datum ab. In
der Faktentabelle wäre das eine partielle Abhängigkeit und würde schon die 2NF
verletzen.

Warum ELT und nicht ETL? Die Daten sind klein und enthalten keine Personendaten.
Deshalb können wir sie roh laden und in BigQuery umbauen. Der Datenschutz-Nachteil
von ELT fällt weg.

Warum fehlen bei der Kasse die Absagen? Die Kasse erfasst nur angenommene
Bestellungen. Ein leeres Feld heisst «unbekannt», nicht «0». Darum legen wir dort keine
Absage-Zeile an, sonst sieht «nicht erfasst» aus wie «keine Absage».

Warum gibt es bei der App Absage-Zeilen mit 0? Bei der App ist 0 ein bekannter Wert:
keine Absage. Diesen Unterschied zu «unbekannt» wollen wir sichtbar halten.

BigQuery prüft PK und FK nicht. Ist das ein Problem? Nein, die Tests prüfen das: keine
doppelten Schlüssel, keine verwaisten Fremdschlüssel.




                                                                                                    Page 5 of 6
Spickzettel – Star Schema & Pipeline Pizzeria Da Luigi




Ist die Lineage-Grafik das Star Schema? Nein. Lineage zeigt, aus welchen Tabellen die
Fakten befüllt wurden (Datenfluss). Das Star Schema zeigt Spalten, Schlüssel und
Kennzahlen (Datenmodell).

Was ist der nächste Schritt? Die Pilotdaten vom 13./14. und 20./21. November laden. Dann
sind die Kanäle getrennt und die Absagen an der Kasse erfasst. Das Modell muss dafür
nicht geändert werden.




                                                                                   Page 6 of 6
```
