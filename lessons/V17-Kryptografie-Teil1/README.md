# V17 – Kryptografie (Teil 1)

Diese Vorlesung führt dich in die Grundlagen der **Kryptografie** ein. Du lernst,
warum Verschlüsselung im Maschinenbau-Alltag wichtig ist (Industriespionage,
DSGVO, sichere Übertragung von CAD-Dateien), verstehst den Unterschied zwischen
**Klartext** und **Geheimtext**, erarbeitest dir die klassische **Caesar-Chiffre**
von Hand und in Python und lernst den fundamentalen Unterschied zwischen
**symmetrischen** und **asymmetrischen** Verfahren kennen.

## 🎯 Lernziele

Nach dieser Vorlesung kannst du …

- die Begriffe **Klartext**, **Geheimtext**, **Schlüssel**, **Verschlüsseln** und **Entschlüsseln** sauber unterscheiden,
- das **Kerckhoffs-Prinzip** erklären und begründen, warum Sicherheit nicht auf einem geheimen Algorithmus beruhen darf,
- die **Caesar-Chiffre** per Hand und in Python anwenden (Formel `(pos + k) % 26`),
- einen **Brute-Force-Angriff** auf Caesar programmieren und die Unsicherheit des Verfahrens einschätzen,
- **symmetrische** Verfahren (z. B. AES) von **asymmetrischen** Verfahren (z. B. RSA) abgrenzen,
- die Python-Funktionen `ord()` und `chr()` sowie den Modulo-Operator `%` sicher einsetzen.

## ⏱️ Zeitbudget gesamt

Rechne mit rund 90 Minuten konzentrierter Selbstlernzeit, verteilt auf
Python-Recap, Theorie, Tutorial und Übungsaufgaben.

## 📚 Reihenfolge

Arbeite die Notebooks **in dieser Reihenfolge** durch:

1. [00_python_recap.ipynb](00_python_recap.ipynb) — Strings, `%`, `ord`/`chr` (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) — Kryptografie-Grundlagen & Caesar (~30 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) — Caesar selbst programmieren (~20 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — Fünf Übungsaufgaben (~25 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/). **Bitte erst reinschauen,
nachdem du es selbst versucht hast.**

## 📦 Voraussetzungen

Du solltest die Inhalte der Vorlesungen V01 bis V16 verinnerlicht haben,
insbesondere **Funktionen** mit `def`/`return` (V10), **Schleifen** über Strings
(V06), **Listen** (V08) und den Umgang mit `try`/`except` (V09). Das
Recap-Notebook frischt String-Handling, Modulo und `ord`/`chr` gezielt auf.

## 🧰 Verwendete Bibliotheken

Für diese Vorlesung brauchst du **keine externen Bibliotheken** – alle
Beispiele kommen mit der Python-Standardbibliothek aus. Im Ordner
[testprogramme/](testprogramme/) liegen aus V16 übernommene Socket-Demos. Diese
werden in V17 nur erwähnt, nicht ausgeführt.

## 🗂️ Diagramme

Alle Mermaid-Diagramme liegen als `.mmd`-Dateien unter [diagramme/](diagramme/)
und werden aus den Notebooks per Python-Zelle geladen.
