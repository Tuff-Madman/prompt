---
name: neuen-prompt-erstellen
description: Erstellt aus einem knappen Vorhaben einen klar strukturierten neuen Prompt mit Ziel, Regeln, Eingaben und Ausgabeformat.
application: manual
trigger: /neuen-prompt-erstellen
---

# Zweck

Forme eine vage oder knappe Aufgabenbeschreibung in einen sauberen, direkt nutzbaren Prompt um.

# Aufgabe

Erstelle auf Basis der Nutzereingabe einen neuen Prompt, der:
- das Ziel eindeutig benennt
- relevante Eingaben und Annahmen sauber trennt
- klare Arbeitsregeln vorgibt
- ein passendes Ausgabeformat festlegt
- unnötige Ausschmückung vermeidet

# Vorgehen

1. Extrahiere das eigentliche Ziel der Anfrage.
2. Benenne fehlende, aber entscheidende Variablen nur dann explizit, wenn sie für die Ausführung notwendig sind.
3. Formuliere den Prompt so, dass er direkt in einem anderen LLM verwendet werden kann.
4. Strukturiere den Prompt in kurze, klare Abschnitte.
5. Nutze präzise Sprache statt allgemeiner Floskeln.

# Ausgabeformat

Liefere genau diese Blöcke in dieser Reihenfolge:

## Prompttitel
Eine kurze, klare Bezeichnung.

## Finaler Prompt
Ein direkt kopierbarer Prompt als Markdown-Codeblock.

## Optionale Variablen
Nur die Platzhalter, die tatsächlich nützlich oder nötig sind.

## Kurzbegründung
2 bis 5 knappe Sätze, warum der Prompt so aufgebaut ist.

# Stilregeln

- Schreibe klar, konkret und ohne Fülltext.
- Bevorzuge operative Formulierungen.
- Erfinde keine Anforderungen, die nicht aus Ziel oder Kontext ableitbar sind.
- Halte den finalen Prompt so allgemein wie möglich, aber so spezifisch wie nötig.
