# V14 – Betriebssysteme & Rechnerarchitektur (Teil 2)

Diese Vorlesung knüpft direkt an V13 an: Nachdem du die **Hardware-Ebene** des Rechners
kennengelernt hast, wenden wir uns nun der **Software-Schicht** zu, die diese Hardware
verwaltet – dem **Betriebssystem**. Du lernst, wie Prozesse und Threads parallel laufen,
wie der **Scheduler** die CPU-Zeit verteilt, wie das Betriebssystem mit Hilfe von
**virtuellem Speicher** einzelnen Programmen den Eindruck unbegrenzter Ressourcen
vermittelt und wie Dateien in einem Dateisystem strukturiert werden. Parallel steigst
du in das `os`-Modul ein und durchsuchst mit Python automatisiert Ordner mit
Maschinen-Messdaten – genau die Aufgabe, die dich im Ingenieur-Alltag oft erwartet.

## 🎯 Lernziele

Nach dieser Vorlesung kannst du …

- die Aufgaben eines **Betriebssystems** benennen und an Alltags-Beispielen aus der Fertigung erklären,
- den **Lebenszyklus eines Prozesses** (Neu, Bereit, Laufend, Wartend, Beendet) beschreiben,
- den Unterschied zwischen **Prozess** und **Thread** in eigenen Worten darstellen,
- die Scheduling-Strategien **FCFS**, **SJF**, **Round Robin** und **Priority** vergleichen,
- das Konzept von **virtuellem Speicher** und **Paging** anhand eines einfachen Beispiels nachvollziehen,
- **Dateisysteme** (Baumstruktur, Pfade, Rechte, Journaling) beschreiben,
- mit dem Python-Modul **`os`** Ordner durchsuchen, Dateien nach Typ filtern und Dateigrößen ermitteln,
- kleine Auswertungs-Skripte schreiben, die Messdaten in einem Verzeichnis automatisch einlesen und zusammenfassen.

## ⏱️ Zeitbudget gesamt

Rechne mit rund 100–120 Minuten konzentrierter Selbstlernzeit, verteilt auf
Python-Recap, Theorie, Tutorial und Übungsaufgaben.

## 📚 Reihenfolge

Arbeite die Notebooks **in dieser Reihenfolge** durch:

1. [00_python_recap.ipynb](00_python_recap.ipynb) — Python-Auffrischung V07 + V08 (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) — Betriebssysteme: Theorie (~35 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) — Praxis: Das `os`-Modul (~25 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — Übungsaufgaben zur Selbstkontrolle (~35 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/). **Bitte erst reinschauen,
nachdem du es selbst versucht hast.**

## 📦 Voraussetzungen

Du solltest die Inhalte der Vorlesungen V01 bis V13 verinnerlicht haben, insbesondere
**Schleifen mit `break`/`continue`** (V07), **List Comprehensions** (V07), **Listen,
Tupel und Slicing** (V08), **`try`/`except`** (V09) sowie **Funktionen** mit `def`
und `return` (V10). Das Recap-Notebook frischt die beiden Kapitel V07 und V08 gezielt
auf. Aus V13 brauchst du das Grundverständnis der **Von-Neumann-Architektur** und
der Speicherhierarchie.

## 🧰 Verwendete Bibliotheken

Für diese Vorlesung verwendest du die Python-Standardbibliothek (`os`, `os.path`,
`pathlib`, `json`, `xml.etree.ElementTree`, `random`) sowie
[matplotlib](https://matplotlib.org/) für die Visualisierungen in den Aufgaben 4 und 5.
Beide Bibliotheken sind in der projektweiten
[`requirements.txt`](../../requirements.txt) enthalten.

## 🧪 Testdaten

Die Übungsaufgaben greifen auf folgende Dateien im Vorlesungsordner zu:

- [`cnc_praezision.csv`](cnc_praezision.csv) – Positionier-Abweichungen von 15 CNC-Maschinen,
- [`werkstoff_pruefung.json`](werkstoff_pruefung.json) – Zugfestigkeit und weitere Kennwerte von Stahl- und Aluminium-Proben nach DIN EN ISO 6892-1,
- [`produktionslinien_vergleich.xml`](produktionslinien_vergleich.xml) – Kennzahlen von fünf Produktionslinien eines Automotive-Zulieferers.

Eine ausführliche Beschreibung der Spalten und Felder findest du in
[TESTDATEN_README.md](TESTDATEN_README.md).

## 💡 Tipps fürs Selbstlernen

Führe jede Code-Zelle tatsächlich aus (`Shift+Enter`), statt den Code nur zu lesen.
Verändere anschließend die Parameter (z. B. den durchsuchten Ordner oder die
Dateiendung), um das Verhalten aktiv zu erkunden. Wenn du nicht weiterkommst,
arbeite zuerst das Recap-Notebook sorgfältig durch – die meisten Stolpersteine
in V14 sind Python-Syntax-Themen aus V07/V08, nicht das Betriebssystem an sich.
