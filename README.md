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

## Prompt file format and structure

Each prompt file must consist of a required YAML frontmatter metadata block followed by a Markdown body containing the prompt itself.

### Frontmatter schema

The frontmatter defines the prompt's identity, high-level intent, activation context, input expectations, allowed tools, lifecycle state, and category assignment.

| Field | Required | Description |
|---|---|---|
| `name` | Yes | The name of the prompt. Must exactly match the file name without the `.prompt.md` extension. Use an ontologically consistent, kebab-case name with hyphens, consistent with existing naming conventions and naming patterns. Maximum 64 characters. Lowercase letters, numbers, and hyphens only. Must not contain XML tags. |
| `description` | Yes | A dense, AI-addressed description of the prompt that captures its high-level intent, context, and primary intended uses. Must be non-empty, must not contain XML tags, and must not exceed 1024 characters. |
| `when_to_use` | No | Additional AI-addressed activation context describing when the prompt should be used, such as trigger phrases, typical user requests, or usage conditions. Use a single string value. A folded multi-line string using `>` is acceptable for longer text. Combined with `description`, this field is hard-capped at 1536 characters. |
| `arguments` | No | The expected prompt arguments as an `argument: description` mapping, where each description should function as a compact input contract by clarifying the argument’s role, expected specificity, whether it is required, optional, or contextually required, and any constraints, suggestions, or selection affordances relevant to how it should be supplied. |
| `argument-hint` | If `arguments` is present | A condensed, argument-oriented guidance string that mirrors the semantic input structure defined in `arguments` at a higher level. If `arguments` is specified, `argument-hint` should also be provided to reflect the same expected input logic in a more compact form. |
| `tools` | No | A list of allowed tool or tool set names, expressed as one string value per list item. |
| `status` | Yes | The current working state of the prompt. Allowed values: `concept`, `draft`, `approved`. |
| `category` | No | The canonical thematic grouping or classification of the prompt, expressed as a single string value. See the category index for allowed values. |

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
