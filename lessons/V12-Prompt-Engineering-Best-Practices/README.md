# V12 – Prompt Engineering: Best Practices

In dieser Vorlesung lernst du, wie du **KI-Werkzeuge wie ChatGPT, Copilot oder Claude
gezielt steuerst**, indem du gute Prompts schreibst. Parallel vertiefst du das Bauen
von Text-Vorlagen mit **f-Strings** und **String-Methoden** (`.strip()`, `.upper()`,
`.lower()`, `.replace()`) – das brauchst du, um Prompts sauber aus Daten zusammenzusetzen.

## 🎯 Lernziele

Nach dieser Vorlesung kannst du …

- in eigenen Worten erklären, was ein **Prompt** ist und wovon die Qualität der Antwort abhängt,
- einen Prompt aus den Bausteinen **Rolle / Kontext / Aufgabe / Format / Beispiele** aufbauen,
- **Zero-Shot**, **Few-Shot** und **Chain-of-Thought** unterscheiden,
- **System-Prompt** und **User-Prompt** voneinander abgrenzen,
- typische Prompt-Fehler (zu vage, zu lang, widersprüchlich) erkennen und vermeiden,
- mit **f-Strings** und String-Methoden (`.strip()`, `.upper()`, `.lower()`, `.replace()`)
  Prompt-Vorlagen in Python erzeugen,
- Prompts **iterativ verbessern**, statt den ersten Wurf zu akzeptieren,
- die **Grenzen** der LLM-Antwort (Halluzinationen, veraltete Daten) einordnen.

## ⏱️ Zeitbudget gesamt

Ca. 100 Minuten Selbstlernzeit.

## 📚 Reihenfolge

Arbeite die Notebooks **in dieser Reihenfolge** durch:

1. [00_python_recap.ipynb](00_python_recap.ipynb) — Python-Auffrischung V03 + V04 (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) — Prompt Engineering: Theorie (~30 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) — Praxis: f-Strings und String-Methoden (~25 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — Übungsaufgaben zur Selbstkontrolle (~30 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/). **Bitte erst reinschauen,
nachdem du es selbst versucht hast.**

## 📦 Voraussetzungen

- Vorlesungen V01–V11 (insbesondere V02 f-Strings, V03 Datentypen, V04 Logische Ausdrücke, V11 LLM-Grundlagen).
- Python-Konzepte: `print()`, `input()`, `if/else`, Variablen, f-Strings, Vergleichs-
  und Logikoperatoren, einfache Funktionsaufrufe, `for`-Schleife, Dateien lesen mit
  `with open(...)`.

## 🧰 Verwendete Bibliotheken

- Nur Python-Standardbibliothek.

## 🧪 Testdaten

- [`produktionsdaten_test.csv`](produktionsdaten_test.csv) – 100 Produktionsdatensätze
  einer CNC-Fertigungszelle (wird in Aufgabe 5 verwendet). Details siehe
  [TESTDATEN_README.md](TESTDATEN_README.md).

## 💡 Tipps fürs Selbstlernen

- Führe jede Code-Zelle wirklich aus (Shift+Enter).
- Ändere Werte in den Demo-Zellen und schau, wie sich die generierten Prompts verändern.
- Teste die erzeugten Prompts ruhig einmal bei einem echten Chatbot (z. B. ChatGPT).
- Bei Fehlern zuerst die Fehlermeldung lesen, dann Prompt anpassen.
