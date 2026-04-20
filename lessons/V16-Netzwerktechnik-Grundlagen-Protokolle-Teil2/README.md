# V16 – Netzwerktechnik-Grundlagen & Protokolle (Teil 2)

Diese Vorlesung vertieft die Netzwerk-Grundlagen aus V15 und verbindet sie mit dem
Werkzeug, mit dem heute in jeder Produktions- und Engineering-Abteilung
Maschinenlogs, Sensor-Reihen und API-Antworten ausgewertet werden: der
Python-Bibliothek **Pandas**. Du lernst, wie eine **REST-API** über **HTTP** mit
**Statuscodes** und **JSON**-Antworten funktioniert, und wie du solche Daten –
offline aus CSV, JSON und XML – mit einem **DataFrame** einliest, filterst,
gruppierst und visualisierst.

## 🎯 Lernziele

Nach dieser Vorlesung kannst du …

- die Rolle von **HTTP**, **Statuscodes** (200, 404, 500) und **JSON** beim
  Datenaustausch zwischen Client und Server erklären,
- die Idee einer **REST-API** anhand typischer Endpunkte wie `/api/sensors`
  beschreiben,
- **Pandas-DataFrames** aus CSV- und JSON-Dateien laden und grundlegende
  Operationen ausführen (`head`, `shape`, `describe`, Spaltenzugriff),
- Daten mit **Boolean-Masken** filtern und mit `groupby` aggregieren,
- einfache **Plots** direkt aus einer Series erzeugen,
- eine XML-Datei mit `xml.etree.ElementTree` in ein DataFrame überführen.

## ⏱️ Zeitbudget gesamt

Rechne mit rund 110–140 Minuten konzentrierter Selbstlernzeit, verteilt auf
Python-Recap, Theorie, Tutorial und Übungsaufgaben.

## 📚 Reihenfolge

Arbeite die Notebooks **in dieser Reihenfolge** durch:

1. [00_python_recap.ipynb](00_python_recap.ipynb) — kurze Auffrischung zu `with open`,
   Listen/Dict-Comprehensions, Funktionen mit Default-Parametern sowie ein erster
   Einstieg in Pandas (~15 Min).
2. [01_theorie.ipynb](01_theorie.ipynb) — Pandas-Grundlagen und
   Netzwerk-Kommunikations-Konzepte (HTTP, REST, JSON-APIs) mit
   Mermaid-Diagrammen (~45 Min).
3. [02_praxis.ipynb](02_praxis.ipynb) — Hands-on mit `sensoren_daten.csv`:
   Einlesen, Filtern, Gruppieren, Plotten (~30 Min).
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — fünf Übungsaufgaben (3⭐, 2⭐⭐)
   auf echten Testdaten (~45 Min).

Lösungen findest du im Ordner [loesungen/](loesungen/) — **erst** reinschauen,
nachdem du es selbst versucht hast.

## 📦 Voraussetzungen

- Vorlesungen V01–V15 (insbesondere V09 Dateien/Exceptions, V10 Funktionen,
  V15 Netzwerk-Grundlagen).
- Grundverständnis von CSV, JSON und XML als Datenformate.

## 🧰 Verwendete Bibliotheken

- **pandas** — Tabellen-Analyse (DataFrame, Series, `groupby`, `read_csv`, `read_json`).
- **matplotlib** — einfache Plots über die DataFrame-Methode `.plot()`.
- **xml.etree.ElementTree** — XML-Parser aus der Standardbibliothek.
- **json** — JSON-Parser aus der Standardbibliothek.
- Kein echter Netzwerk-Call: `requests` wird nur **konzeptionell** gezeigt, nie live aufgerufen.

## 🧪 Testdaten

Siehe [TESTDATEN_README.md](TESTDATEN_README.md) für die vollständige Beschreibung.

- `sensoren_daten.csv` — 15 Sensor-Messungen (Temperatur, Vibration, Druck, Status).
- `wartungsauftraege.json` — 10 Wartungsaufträge mit Priorität, Kosten, Status.
- `produktionsplanung.xml` — 6 Produktionsaufträge auf 3 Linien.
- `produkte_katalog.csv` — 10 mechanische Komponenten mit Preis, Kategorie.
