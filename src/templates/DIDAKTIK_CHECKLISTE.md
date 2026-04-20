# Didaktik-Checkliste für V11–V20

Diese Checkliste ist **verbindlich** für jede überarbeitete Vorlesung. Jeder Subagent
muss vor Abgabe alle Punkte abhaken.

## Grundprinzipien

- **Selbstlernen steht im Zentrum.** Studierende arbeiten die Notebooks allein durch.
- **Mikro-Schritte statt Monolog.** Jeder neue Gedanke bekommt seine eigene Zelle mit
  Beispiel und direkt ausführbarem Code.
- **Lieber weniger und verstanden, als viel und verloren.** Theorie radikal kürzen,
  nur was für die Aufgaben nötig ist. Alles andere unter „Weiterführend" verlinken
  oder weglassen.
- **Ausprobieren > Lesen.** Nach max. 2 Text-Zellen folgt immer eine Code-Zelle.
- **Kein Maschinenbau-Bezug um jeden Preis.** Situativ, wo er natürlich passt.

## Struktur pro Vorlesung (verbindlich)

```
lessons/VXX-Thema/
├── README.md                       # Übersicht, Lernziele, Reihenfolge
├── 00_python_recap.ipynb           # Nur V11–V15: Kompaktes Python-Recap (~10–15 Zellen)
├── 01_theorie.ipynb                # Stark gekürzte Theorie
├── 02_praxis.ipynb                 # Tutorial mit Mikro-Schritten
├── 03_aufgaben.ipynb               # 3⭐ + 2⭐⭐ mit Starter-Code & asserts
├── loesungen/
│   ├── 02_praxis_loesung.ipynb     # (optional) Lösungen zu Fill-in-Blanks
│   └── 03_aufgaben_loesung.ipynb   # Vollständige Lösungen
└── <Testdaten unverändert>         # CSV/JSON/XML/TXT bleiben
```

## Pflichtbestandteile jedes Notebooks

### Kopfzelle (Markdown, immer erste Zelle)

```markdown
# VXX – <Thema>: <Notebook-Titel>

## 🎯 Lernziele
Nach diesem Notebook kannst du …
- …
- …
- …

## ⏱️ Zeitbudget
Ca. XX Minuten.

## 🧭 TL;DR
<2–3 Sätze, die das Wichtigste zusammenfassen.>

## 📦 Voraussetzungen
- VXX-Thema (vorherige Vorlesung)
- <ggf. Python-Konzepte, siehe python_topics.md>
```

### Fußzelle (Markdown, immer letzte Zelle)

```markdown
## ✅ Zusammenfassung
- Punkt 1
- Punkt 2

## ➡️ Nächster Schritt
Weiter mit [02_praxis.ipynb](02_praxis.ipynb) (bzw. nächstes Notebook).
```

## Aufgaben-Notebook (`03_aufgaben.ipynb`)

- **Genau 5 Aufgaben**: 3 × ⭐ (sehr einfach), 2 × ⭐⭐ (mittel). **Keine ⭐⭐⭐.**
- Jede Aufgabe hat:
  1. Markdown-Zelle mit Titel, Schwierigkeit, Kontext, Aufgabenstellung, erwartete Ausgabe
  2. Bei Aufgaben mit **nicht-trivialem Ablauf** (Fallunterscheidung, Schleife,
     mehrere Schritte) zusätzlich ein **Programmablaufplan (PAP)** als ausgelagertes
     Mermaid-Diagramm (`diagramme/aufgabe_N_pap.mmd`), eingebunden mit einer
     Python-Zelle wie oben. Triviale Einzeiler brauchen keinen PAP.
  3. Code-Zelle mit **Starter-Code** (nicht leer!), TODOs markiert mit `# TODO: …`
  4. Code-Zelle mit `assert`-Selbstkontrolle und Klartext-Feedback
- PAPs folgen DIN 66001 / ISO 5807 sinngemäß: Ovale für Start/Ende, Rechtecke für
  Verarbeitung, Rauten für Verzweigungen.

### ⚠️ Starter-Code muss ausführbar sein

`nbconvert --execute` bricht ab, sobald eine Zelle einen `TypeError` wirft. Die
Selbstkontroll-`try/except` greift erst, wenn die Starter-Zelle ohne Exception durchläuft.

- **Gut**: `ergebnis = 0` oder `return None` oder `return sum(werte)` mit Kommentar `# TODO: stimmt noch nicht`.
- **Schlecht**: `ergebnis = ...` gefolgt von `ergebnis * 2` — das wirft zur Laufzeit `TypeError`.
- Verwende `...` nur als **reine Zuweisung ohne Folge-Operation**, sonst lieber sinnvollen Default-Wert + TODO-Kommentar.
- Beispiel einer assert-Zelle:

```python
# ▶️ Selbstkontrolle – einfach ausführen
try:
    assert ergebnis == 42, f"Erwartet 42, bekommen: {ergebnis}"
    print("✅ Richtig! Du hast die Aufgabe gelöst.")
except AssertionError as e:
    print(f"❌ Noch nicht ganz: {e}")
except NameError:
    print("❌ Die Variable `ergebnis` existiert noch nicht. Hast du den TODO gelöst?")
```

## Praxis-Notebook (`02_praxis.ipynb`)

- Gliederung in **kleine Abschnitte** (je 1 Konzept).
- Nach max. 2 Text-Zellen eine **Code-Zelle zum direkten Ausprobieren**.
- Mindestens 2–3 **Fill-in-the-blanks** (`# TODO:`) mit asserts als Selbstkontrolle.
- Am Ende jedes Abschnitts eine **Mini-Challenge** (eine Zeile Aufgabe, eine assert-Zelle).

## Theorie-Notebook (`01_theorie.ipynb`)

- **Richtwert ca. 50–60 Text-Zellen insgesamt.** Erklärungen dürfen ausführlich sein –
  lieber ein Konzept zweimal aus verschiedenen Blickwinkeln beleuchten, als zu knapp
  bleiben. Studierende sollen die Theorie ohne Dozent verstehen können.
- Jedes Konzept in **1–2 Absätzen** + wo möglich Mini-Code-Demo, Diagramm oder
  konkretes Beispiel aus dem Ingenieur-Alltag.
- **Mermaid-Diagramme** für Strukturen/Abläufe bevorzugt – siehe Abschnitt
  „Mermaid-Diagramme" unten.
- Was nicht unbedingt nötig ist, geht in eine **Blockquote-Box „💡 Weiterführend"**
  und ist optional.
- Keine Aufgaben hier — nur Verständnis-Fragen mit aufklappbaren Antworten als
  Markdown-Details.

### Mermaid-Diagramme – immer in eigene Datei

Mermaid-Quelltext wird **nicht** direkt in Markdown-Zellen geschrieben, sondern in
eigene `.mmd`-Dateien unter `lessons/VXX-.../diagramme/` ausgelagert. Das hat zwei
Vorteile: Die Diagramme sind auch außerhalb der Notebooks nutzbar (Präsentation,
README, Prüfungsmaterial), und die Single-Source-of-Truth verhindert Abweichungen.

**Konvention:**

- Ordner: `lessons/VXX-.../diagramme/`
- Dateinamen: `NN_kurzname.mmd` (z. B. `01_ki_vs_klassisch.mmd`)
- Einbindung im Notebook über eine **Python-Zelle** direkt unter der erklärenden
  Markdown-Zelle:

```python
from IPython.display import Markdown, display
with open("diagramme/01_ki_vs_klassisch.mmd", encoding="utf-8") as f:
    display(Markdown(f"```mermaid\n{f.read()}\n```"))
```

Die Zelle rendert in VS Code (Jupyter-Extension) als echtes Mermaid-Diagramm. In
anderen Umgebungen sieht man zumindest den Quelltext. Parallel kann ein Link
`[Diagramm-Quelle](diagramme/01_ki_vs_klassisch.mmd)` in der Markdown-Zelle stehen.

## README.md pro Vorlesung (Pflicht)

```markdown
# VXX – <Thema>

<1–2 Sätze Einordnung>

## 🎯 Lernziele
- …

## ⏱️ Zeitbudget gesamt
Ca. 90–120 Minuten Selbstlernzeit.

## 📚 Reihenfolge
1. [01_theorie.ipynb](01_theorie.ipynb) — Theorie-Grundlagen (~XX Min)
2. [02_praxis.ipynb](02_praxis.ipynb) — Praxis / Tutorial (~XX Min)
3. [03_aufgaben.ipynb](03_aufgaben.ipynb) — Übungsaufgaben (~XX Min)

Lösungen findest du im Ordner [loesungen/](loesungen/) — **erst** reinschauen,
nachdem du es selbst versucht hast.

## 📦 Voraussetzungen
- Vorlesungen V01–V(XX-1)
- Python-Konzepte: …

## 🧰 Verwendete Bibliotheken
- …

## 🧪 Testdaten
- …
```

## Umgang mit alten Dateien

- `_skript.md`, `_aufgaben.md`, `_loesungen.md`, `*_alt.md`, bestehendes
  `VXX_notebook.ipynb` werden **gelöscht** (Git-History reicht).
- **Testdaten bleiben erhalten** (CSV, JSON, XML, TXT, Unterordner `testdaten/`,
  `testprogramme/`). Relative Pfade in neuen Notebooks entsprechend anpassen.

### 📂 Pfad-Konvention für Testdaten

- Notebooks im Vorlesungsordner referenzieren Testdaten direkt: `"lager_daten.csv"`.
- Notebooks unter `loesungen/` brauchen `../`: `"../lager_daten.csv"`.
- Immer relativ zum Notebook, niemals absolut.

## Python-Konzept-Progression

- Keine Python-Konzepte verwenden, die laut [python_topics.md](../../python_topics.md)
  noch nicht eingeführt wurden.
- Bei neu eingeführten Konzepten eine kurze Mini-Einführung im Notebook geben.

### 🧠 Python-Recap in V11–V15 (verbindlich)

Weil in V01–V10 viele Python-Basics im Live-Unterricht zu schnell vermittelt wurden,
bekommt **jede** Vorlesung V11–V15 ein zusätzliches Notebook `00_python_recap.ipynb`,
das die **wichtigsten** Inhalte aus jeweils zwei früheren Vorlesungen kompakt auffrischt.

**Feste Zuordnung (chronologisch):**

| Vorlesung | Recap-Themen aus | Inhaltliche Schwerpunkte (Pflicht) |
|---|---|---|
| V11 | V01 + V02 | Variablen, `print`, `input`, `int/float/str`, Arithmetik; f-Strings, `with open(...)`, `.strip`, `.split` |
| V12 | V03 + V04 | `type`, `isinstance`, `bool`, `round`, `min`, `max`; Vergleichs- und Logikoperatoren (`==`, `!=`, `and`, `or`, `not`), verkettete Vergleiche, Truthy/Falsy |
| V13 | V05 + V06 | `if`/`elif`/`else`, Ternär-Operator, Einrückung; `for`/`while`, `range`, `enumerate`, Akkumulation |
| V14 | V07 + V08 | `break`, `continue`, List Comprehensions, `random`-Modul; Listen & Tupel, wichtigste List-Methoden, Slicing, `zip`, `sum/all/any` |
| V15 | V09 + V10 | `try`/`except`/`else`/`finally`, `raise`, wichtige Exception-Typen; `def`/`return`, Default- und Keyword-Parameter, LEGB-Scope, Docstrings |

**Regeln für `00_python_recap.ipynb`:**

- **Umfang ca. 10–15 Zellen** (kompakt, nicht ausschweifend).
- Beginnt mit Kopfzelle analog anderen Notebooks (🎯 Lernziele, ⏱️ ~15 Min, Scope-Info).
- Pro Teilthema: max. 1 Erklärungs-Zelle + 1 Demo-Code-Zelle.
- **1–2 Mini-Übungen** mit Starter-Code und assert-Zelle (`try/except AssertionError`!).
- Schließt mit Cheat-Sheet-Tabelle und Verweis auf `01_theorie.ipynb`.
- README.md führt das Recap als **ersten** Schritt in der Reihenfolge auf.
- Läuft via `nbconvert --execute` fehlerfrei durch.
- Rekapituliert **nur** die in der Tabelle genannten Schwerpunkte — keine neuen
  Konzepte einführen.

## Technisches

- Kernel-Name: `python3`.
- Alle Notebooks müssen mit `jupyter nbconvert --to notebook --execute <notebook>`
  fehlerfrei durchlaufen (mit vorhandenem `requirements.txt`).
- Keine absoluten Pfade zu Testdaten — immer relativ zum Notebook.
- Keine Plots, die externe Fenster öffnen. `plt.show()` nur am Ende eines Blocks,
  sonst inline.

## Review-Checkliste (abhakbar)

- [ ] README.md vorhanden, verlinkt alle Notebooks korrekt
- [ ] Nur V11–V15: `00_python_recap.ipynb` vorhanden, ca. 10–15 Zellen, Themen gemäß Zuordnungstabelle
- [ ] Kopfzelle jedes Notebooks enthält 🎯 Lernziele, ⏱️ Zeitbudget, 🧭 TL;DR
- [ ] Fußzelle jedes Notebooks enthält ✅ Zusammenfassung und ➡️ Nächster Schritt
- [ ] Theorie-Notebook ca. 50–60 Text-Zellen, gründliche Erklärungen
- [ ] Alle Mermaid-Diagramme liegen als `.mmd`-Datei unter `diagramme/` und werden
      im Notebook per Python-Zelle geladen
- [ ] Praxis-Notebook hat mind. 2 Fill-in-Blanks mit asserts
- [ ] Aufgaben-Notebook: genau 3⭐ + 2⭐⭐, jede mit Starter-Code und assert-Zelle
- [ ] Bei Aufgaben mit nicht-trivialem Ablauf PAP als `.mmd`-Datei vorhanden
- [ ] Lösungs-Notebook(s) unter `loesungen/` vorhanden
- [ ] Alle alten `_skript.md`/`_aufgaben.md`/`_loesungen.md`/`*_alt.md` entfernt
- [ ] Testdaten-Dateien erhalten und Pfade funktionieren
- [ ] Keine Python-Konzepte vor ihrer Einführung laut python_topics.md
- [ ] Jedes Notebook läuft via `jupyter nbconvert --execute` fehlerfrei durch
