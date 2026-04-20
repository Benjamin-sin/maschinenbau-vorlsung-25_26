# V19 – Datenbanken Teil 1: SQLite-Grundlagen

Nachdem du in V08 und V09 **Listen**, **Dictionaries** und die Serialisierung nach
CSV und JSON kennengelernt hast, wird es Zeit für den nächsten Schritt: eine echte
**Datenbank**. Mit **SQLite** und dem Standardmodul `sqlite3` lernst du in dieser
Vorlesung, wie man strukturierte Daten persistent speichert, sie mit **SQL**
abfragt und ändert und warum das zuverlässiger ist als eine wachsende Sammlung von
CSV-Dateien.

## 🎯 Lernziele

- Du erklärst den Unterschied zwischen einer flachen Datei (CSV/JSON) und einer
  relationalen Datenbank und kennst die Vorteile letzterer.
- Du erstellst mit `CREATE TABLE` eine Tabelle mit passenden **Datentypen** und
  Integritätsbedingungen wie `PRIMARY KEY` und `NOT NULL`.
- Du fügst Daten mit `INSERT`, liest sie mit `SELECT` (inklusive `WHERE`,
  `ORDER BY`, `LIMIT`), änderst sie mit `UPDATE` und löschst sie mit `DELETE`.
- Du bindest Python an eine SQLite-Datenbank mit `sqlite3.connect`, arbeitest mit
  `cursor()` und `execute()` und weißt, warum **Parameter-Binding** (`?`) die
  einzige akzeptable Methode gegen **SQL-Injection** ist.
- Du liest eine CSV-Datei ein und überträgst ihre Inhalte in eine SQLite-Tabelle.

## ⏱️ Zeitbudget gesamt

Ca. 90–120 Minuten Selbstlernzeit.

## 📚 Reihenfolge

1. [00_python_recap.ipynb](00_python_recap.ipynb) — Auffrischung `with`-Kontext,
   Tupel-Entpacken, `csv.DictReader`, f-Strings (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) — Relationales Modell, SQL-Grundlagen,
   sqlite3-Modul, SQL-Injection (~30 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) — Tutorial mit In-Memory-DB (~25 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — 5 Übungsaufgaben (~40 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/) — **erst** reinschauen,
nachdem du es selbst versucht hast.

## 📦 Voraussetzungen

- Vorlesungen V01–V18, insbesondere **Listen und Tupel** (V08), **CSV-Lesen**
  (V09) sowie **Funktionen** und **Fehlerbehandlung** (V09/V10).
- Python-Konzepte: `with`-Kontext-Manager, Tupel-Entpacken, f-Strings,
  `csv.DictReader`.

## 🧰 Verwendete Bibliotheken

- `sqlite3` aus der Python-Standardbibliothek (keine externe Installation nötig).
- `csv` für den Import aus `produkte.csv`.

## 🧪 Testdaten

Alle Testdaten liegen im Unterordner [testdaten/](testdaten/). In dieser Vorlesung
verwenden wir primär:

- `produkte.csv` — 6 Produkte mit ID, Name, Produktionszeit und Materialbedarf.

Weitere Testdaten (`sensoren.csv`, `werkstoffe.csv`, `zugversuche.csv`, …) sind
vorbereitet und werden in **V20** (Datenbanken Teil 2) intensiver genutzt.

## 🗄️ Hinweis: Keine persistente `.db`-Datei

Alle Beispiele und Aufgaben arbeiten mit einer **In-Memory-Datenbank**
(`sqlite3.connect(":memory:")`). So bleibt dein Projektordner sauber, und du
kannst jede Zelle beliebig oft neu ausführen, ohne dass Altdaten im Weg stehen.
