# V20 – Datenbanken Teil 2: JOINs, GROUP BY, Aggregate

Aufbauend auf **V19** (Tabellen, einfache `SELECT`/`INSERT`/`UPDATE`/`DELETE`)
behandelt diese Vorlesung die Werkzeuge, mit denen man aus mehreren Tabellen
echte Kennzahlen gewinnt: **JOINs**, **GROUP BY** mit **Aggregatfunktionen**,
**Subqueries**, **Views**, **Indizes** und **Transaktionen**.

## 🎯 Lernziele

- Du erklärst die Grundidee der **Normalisierung** (1NF/2NF/3NF) und wofür sie gut ist.
- Du verknüpfst Tabellen mit **Fremdschlüsseln** und `INNER JOIN` / `LEFT JOIN` und benennst den Unterschied.
- Du setzt `GROUP BY` zusammen mit `COUNT`, `SUM`, `AVG`, `MIN`, `MAX` ein, um Kennzahlen pro Kategorie zu berechnen.
- Du trennst sauber zwischen `WHERE` (Zeilenfilter) und `HAVING` (Gruppenfilter).
- Du erkennst **Subqueries**, **Views** und **Indizes** und kannst ihre jeweilige Rolle erklären.
- Du verstehst **Transaktionen** mit `BEGIN`/`COMMIT`/`ROLLBACK` und die ACID-Eigenschaften.

## ⏱️ Zeitbudget gesamt

Ca. 110 Minuten Selbstlernzeit.

## 📚 Reihenfolge

1. [00_python_recap.ipynb](00_python_recap.ipynb) – `dict`/`list[dict]`, `sorted` mit `key=lambda`, `sqlite3`-Refresher (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) – Normalisierung, JOINs, GROUP BY, HAVING, Subqueries, Views, Indizes, Transaktionen (~35 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) – Schritt-für-Schritt-Tutorial mit eigener deterministischer In-Memory-DB (~25 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) – 5 Übungsaufgaben (3⭐, 2⭐⭐) (~40 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/) – **erst** reinschauen,
nachdem du es selbst versucht hast.

## 📦 Voraussetzungen

- Vorlesungen V01–V19, insbesondere V19 (SQL-Grundlagen, `sqlite3`, Parameter-Binding).
- Python-Konzepte: `dict`, `list[dict]`, `sorted`/`max`/`min` mit `key`, List-Comprehensions, `with`-Kontext, f-Strings.

## 🧰 Verwendete Bibliotheken

- `sqlite3` aus der Python-Standardbibliothek (keine externe Installation nötig).
- `IPython.display` für die eingebetteten Mermaid-Diagramme.

## 🗄️ Hinweis: Keine persistente `.db`-Datei

Alle Notebooks verwenden **ausschließlich** eine In-Memory-Datenbank
(`sqlite3.connect(":memory:")`), die in einer Helper-Funktion `setup_db()` mit
**deterministischen** Testdaten (5 Maschinen, 8 Wartungen) gefüllt wird. So
bleibt der Projektordner sauber, und jede Zelle startet aus exakt demselben
Zustand – die `assert`-Selbstkontrollen sind damit reproduzierbar.

Die Datei `testdaten/init_produktionsdb.py` liegt als Referenz bei, wird von den
Notebooks aber **nicht** verwendet (sie nutzt `random` ohne festen Seed und wäre
daher nicht deterministisch).

## 🗺️ Mermaid-Diagramme

Unter [diagramme/](diagramme/) liegen sechs `.mmd`-Dateien, die in den Notebooks
dynamisch eingebunden werden:

- `01_inner_join.mmd`, `02_left_join.mmd` – Visualisierung der beiden JOIN-Typen
- `03_group_by.mmd` – Gruppierung als Datenfluss
- `04_having_vs_where.mmd` – Reihenfolge von Zeilen- und Gruppenfilter
- `aufgabe_4_pap.mmd`, `aufgabe_5_pap.mmd` – Programmablaufpläne zu den ⭐⭐-Aufgaben
