# V13 – Betriebssysteme & Rechnerarchitektur (Teil 1)

In dieser Vorlesung lernst du, wie ein Computer im Inneren aufgebaut ist. Du
verstehst die **Von-Neumann-Architektur**, den Zusammenspiel von **CPU**, **RAM**,
**Cache**, **Bussystem** und **I/O**, und warum diese Hardware-Ebene für
Ingenieurs-Anwendungen (Messdatenerfassung, FEM-Simulation, CNC-Steuerung)
unmittelbar praxisrelevant ist. Parallel steigst du in die Bibliothek
**matplotlib** ein und erstellst deine ersten **Balkendiagramme**.

## 🎯 Lernziele

Nach dieser Vorlesung kannst du …

- die fünf Grundbausteine der **Von-Neumann-Architektur** benennen und ihr Zusammenspiel erklären,
- die **Speicherhierarchie** (Register, L1/L2/L3-Cache, RAM, SSD, HDD) mit Größen- und Geschwindigkeitsordnungen einordnen,
- den **Fetch-Decode-Execute-Zyklus** der CPU in eigenen Worten beschreiben,
- begründen, warum **Cache-Lokalität** die Laufzeit von Mess- und Simulationsprogrammen drastisch beeinflusst,
- **Daten-**, **Adress-** und **Steuerbus** unterscheiden,
- mit **matplotlib** (`plt.bar`, `plt.title`, `plt.xlabel`, `plt.ylabel`, `plt.show`) ingenieurnahe Balkendiagramme erzeugen,
- kleine Ingenieur-Datensätze (Werkzeugverschleiß, Hydraulikdruck, Lagerschwingung) visuell aufbereiten.

## ⏱️ Zeitbudget gesamt

Rechne mit rund 100–120 Minuten konzentrierter Selbstlernzeit, verteilt auf
Python-Recap, Theorie, Tutorial und Übungsaufgaben.

## 📚 Reihenfolge

Arbeite die Notebooks **in dieser Reihenfolge** durch:

1. [00_python_recap.ipynb](00_python_recap.ipynb) — Python-Auffrischung V05 + V06 (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) — Rechnerarchitektur: Theorie (~35 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) — Praxis: Einstieg in matplotlib (~25 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — Übungsaufgaben zur Selbstkontrolle (~35 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/). **Bitte erst reinschauen,
nachdem du es selbst versucht hast.**

## 📦 Voraussetzungen

Du solltest die Inhalte der Vorlesungen V01 bis V12 verinnerlicht haben,
insbesondere **Variablen**, **Datentypen** (V01, V03), **f-Strings** (V02),
**logische Ausdrücke** (V04), **Verzweigungen** (V05) und **Schleifen** (V06).
Das Recap-Notebook frischt die beiden letztgenannten Kapitel gezielt auf.

## 🧰 Verwendete Bibliotheken

Für die praktischen Abschnitte benötigst du ausschließlich die Python-
Standardbibliothek sowie [matplotlib](https://matplotlib.org/), die bereits in
der projektweiten [`requirements.txt`](../../requirements.txt) enthalten ist.

## 🧪 Testdaten

Die Übungsaufgabe zur Lager-Schwingungsanalyse nutzt die Datei
[`lager_vibrationsdaten.csv`](lager_vibrationsdaten.csv). Eine ausführliche
Beschreibung der Spalten und Zustandsklassen findest du in
[TESTDATEN_README.md](TESTDATEN_README.md).

## 💡 Tipps fürs Selbstlernen

Führe jede Code-Zelle tatsächlich aus (`Shift+Enter`), statt den Code nur zu
lesen. Verändere anschließend die Werte in den Demo-Zellen, um das Verhalten
des Codes aktiv zu erkunden. Bei Fehlermeldungen lies die Fehlerzeile sorgfältig
und orientiere dich am roten Pfeil — Python zeigt meistens sehr präzise, wo das
Problem steckt.
