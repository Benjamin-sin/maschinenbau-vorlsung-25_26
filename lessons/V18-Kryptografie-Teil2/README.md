# V18 – Kryptografie Teil 2: Hashes, Passwörter, digitale Signaturen

Nachdem du in V17 mit der **Caesar-Chiffre** ein symmetrisches Verschlüsselungs-Verfahren
von Hand nachgebaut hast, geht es in dieser Vorlesung um eine ganz andere
kryptografische Primitive: die **Hash-Funktion**. Hashes sind die Grundlage für die
sichere Speicherung von Passwörtern, für **Integritätsprüfungen** von Firmware-Updates
und für **digitale Signaturen**. Wir nutzen das Python-Standardmodul `hashlib` und
führen zusätzlich einen einfachen **Wörterbuch-Angriff** durch, um die Angreifer-Seite
hautnah zu erleben.

## 🎯 Lernziele

- Du kennst die drei zentralen Eigenschaften kryptografischer Hash-Funktionen
  (Einwegfunktion, deterministisch, **Lawineneffekt**) und kannst sie an konkreten
  Beispielen demonstrieren.
- Du berechnest mit `hashlib` MD5- und SHA-256-Hashes von Strings und Dateien und
  weißt, warum MD5 heute als unsicher gilt.
- Du implementierst einen einfachen **Wörterbuch-Angriff** auf einen Passwort-Hash.
- Du erklärst das Prinzip einer **digitalen Signatur** (Hash + asymmetrische
  Verschlüsselung) und verstehst, warum ein Roboterarm eine Firmware-Signatur prüft,
  bevor er das Update installiert.

## ⏱️ Zeitbudget gesamt

Ca. 90–120 Minuten Selbstlernzeit.

## 📚 Reihenfolge

1. [00_python_recap.ipynb](00_python_recap.ipynb) — Auffrischung `bytes`/`str`,
   Listen-Lookup, Dateien im Binärmodus (~15 Min)
2. [01_theorie.ipynb](01_theorie.ipynb) — Hash-Grundlagen, Angriffe, digitale
   Signaturen (~30 Min)
3. [02_praxis.ipynb](02_praxis.ipynb) — Tutorial mit `hashlib` (~25 Min)
4. [03_aufgaben.ipynb](03_aufgaben.ipynb) — 5 Übungsaufgaben (~40 Min)

Lösungen findest du im Ordner [loesungen/](loesungen/) — **erst** reinschauen,
nachdem du es selbst versucht hast.

## 📦 Voraussetzungen

- Vorlesungen V01–V17, insbesondere Funktionen (V09), Dateizugriff (V11-Recap) und
  die Idee symmetrischer Verschlüsselung aus V17.
- Python-Konzepte: Strings, Listen, `for`-Schleifen, `if`/`return`.

## 🧰 Verwendete Bibliotheken

- `hashlib` aus der Python-Standardbibliothek (keine externe Installation nötig).
- `json` für das Einlesen der Firmware-Meta-Datei.

## 🧪 Testdaten

Alle Testdaten liegen im Unterordner [testdaten/](testdaten/):

- `firmware_v2.3.0.bin` — simulierte Roboter-Firmware (524.288 Bytes) für die
  Integritäts-Prüfung in Aufgabe 5.
- `firmware_v2.3.0_signature.json` — Meta-Datei mit angeblichem SHA-256-Hash,
  Signatur-Informationen und Changelog. **Achtung**: Der `sha256_hash`-Eintrag in der
  JSON-Datei ist ein **Demo-Platzhalter** und stimmt **nicht** mit dem tatsächlichen
  Hash der `.bin`-Datei überein. Berechne den Hash im Notebook selbst.
