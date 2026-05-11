# prompt

Kleines Repository für dateibasierte Prompts.

## Zweck

Dieses Repo sammelt einzelne Prompts als Markdown-Dateien, damit sie klar versionierbar, wiederverwendbar und leicht erweiterbar bleiben.

## Struktur

```text
prompts/
  <promptname>.md
README.md
```

## Format eines Prompts

Jeder Prompt liegt als eigene Datei unter `prompts/` und beginnt idealerweise mit Frontmatter.

```yaml
---
name: beispiel-prompt
description: Kurzbeschreibung des Zwecks
application: manual
trigger: /beispiel-prompt
---
```

Danach folgt der eigentliche Prompt-Inhalt als normales Markdown.

## Konventionen

- Eine Datei pro Prompt
- Dateiname möglichst nah am `name`
- Kurze, klare `description`
- `trigger` optional, aber sinnvoll bei slash-basiertem Aufruf
- Inhalt operativ, knapp und direkt nutzbar formulieren

## Neuer Prompt

1. Neue Datei unter `prompts/` anlegen
2. Frontmatter ergänzen
3. Zweck, Aufgabe, Vorgehen und Ausgabeformat sauber strukturieren
4. Prompt committen

## Beispiel

```text
prompts/neuen-prompt-erstellen.md
```

## Zielbild

Das Repo soll eine einfache, saubere Prompt-Bibliothek bleiben und kein chaotischer Abladeort für halbgare Textfragmente werden.
