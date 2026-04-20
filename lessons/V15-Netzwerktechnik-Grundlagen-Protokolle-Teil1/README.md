# V15 – Netzwerktechnik-Grundlagen & Protokolle (Teil 1)

Diese Vorlesung führt dich in die Grundlagen moderner **Rechnernetze** ein und zeigt
am Beispiel einer Produktionshalle, wie Maschinen heute untereinander sprechen. Du
lernst das **OSI-Modell** als Denk-Raster kennen, verstehst den **TCP/IP-Stack** als
praktische Umsetzung und siehst, welche Rolle **IP-Adressen**, **Ports** und
**Protokolle** im Ingenieur-Alltag spielen. Parallel übst du, mit einfachen
Python-Funktionen offline abgelegte Netzwerk-Protokolldaten (CSV, JSON, XML) zu
analysieren – genau so, wie es in einer SCADA-Leitwarte passiert.

## 🎯 Lernziele

Nach dieser Vorlesung kannst du …

- die Aufgaben und Schichten des **OSI-Modells** benennen und vom **TCP/IP-Stack** abgrenzen,
- den Aufbau einer **IPv4-Adresse** sowie die Bedeutung von **Subnetz**, **Netz-** und **Host-Anteil** erklären,
- typische **Portnummern** (HTTP 80, HTTPS 443, Modbus TCP 502, MQTT 1883, OPC UA 4840) wiedererkennen,
- **TCP** und **UDP** anhand ihrer Eigenschaften unterscheiden,
- die Rolle von **DNS** im Alltag und die Einordnung industrieller Protokolle wie **Modbus TCP**, **OPC UA** und **EtherNet/IP** beschreiben,
- eigene **Python-Funktionen** mit `def` und `return` schreiben und die String-Methoden `.split()`, `.startswith()`, `.isdigit()` sinnvoll einsetzen,
- kleine Analyse-Skripte auf CSV-, JSON- und XML-Netzwerk-Logs anwenden.

## ⏱️ Zeitbudget gesamt

Rechne mit rund 100–120 Minuten konzentrierter Selbstlernzeit, verteilt auf
Python-Recap, Theorie, Tutorial und Übungsaufgaben.

## 📚 Reihenfolge

Arbeite die Notebooks **in dieser Reihenfolge** durch:

1. [00_python_recap.ipynb](00_python_recap.ipynb) — Python-Auffrischung V09 + V10 (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) — Netzwerk-Grundlagen: Theorie (~35 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) — Praxis: Funktionen für Netzwerk-Daten (~25 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — Übungsaufgaben zur Selbstkontrolle (~35 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/). **Bitte erst reinschauen,
nachdem du es selbst versucht hast.**

## 📦 Voraussetzungen

Du solltest die Inhalte der Vorlesungen V01 bis V14 verinnerlicht haben, insbesondere
**`try`/`except`** (V09), **Funktionen** mit `def`/`return` (V10), **Listen- und
Dict-Zugriffe** (V08) sowie den Umgang mit dem **`os`-Modul** (V14). Das
Recap-Notebook frischt V09 und V10 gezielt auf.

## 🧰 Verwendete Bibliotheken

Für diese Vorlesung reichen Teile der Python-Standardbibliothek (`json`,
`xml.etree.ElementTree`, `csv`). **Es werden bewusst keine echten
Netzwerk-Aufrufe** (kein `requests`, kein `socket.connect`) verwendet – alle
Daten liegen als Offline-Log-Dateien im Vorlesungsordner. Echte API-Aufrufe folgen
in V16.

## 🧪 Testdaten

Die Übungsaufgaben greifen auf folgende Dateien im Vorlesungsordner zu:

- [`netzwerk_pakete.csv`](netzwerk_pakete.csv) – 100 Netzwerk-Pakete einer Produktionshalle über fünf Minuten,
- [`maschinenkommunikation.json`](maschinenkommunikation.json) – Konfiguration und Kommunikationsmetriken für zehn Maschinen,
- [`opc_ua_daten.xml`](opc_ua_daten.xml) – XML-Dump eines OPC-UA-Servers mit fünf Maschinenknoten.

Eine ausführliche Beschreibung der Spalten und Felder findest du in
[TESTDATEN_README.md](TESTDATEN_README.md).

## 💡 Tipps fürs Selbstlernen

Führe jede Code-Zelle tatsächlich aus (`Shift+Enter`), statt den Code nur zu lesen.
Wenn dir ein Netzwerk-Begriff nicht vertraut vorkommt, zeichne dir das
OSI-Diagramm aus `diagramme/01_osi_modell.mmd` auf einem Schmierblatt nach und
ordne jedem Begriff eine Schicht zu – dieser aktive Transfer bleibt deutlich
besser im Gedächtnis als reines Lesen.
