<!-- AI-NOTE: All hidden comments in this file using the `AI-NOTE:` prefix are AI-addressed internal guidance for usage, application, decision-making, reasoning, maintenance, and future specification work. They should not be understood or treated as user-addressed comments or as part of the document’s user-facing content. -->

# About this repository

This repository contains reusable prompts and is intended to support consistent authoring, organization, reuse, and extension across prompt files.

Each prompt is maintained as a Markdown prompt file with the strictly required `.prompt.md` extension.

## Prompt file format and structure

Each prompt file must consist of a required YAML frontmatter metadata block followed by a Markdown body containing the prompt itself.

### Frontmatter schema

The frontmatter defines the prompt's identity, high-level intent, activation context, input expectations, allowed tools, lifecycle state, and category assignment.

| Field | Required | Description |
|---|---|---|
| `name` | Yes | The name of the prompt. Must exactly match the file name without the `.prompt.md` extension. Use an ontologically consistent, kebab-case name with hyphens, consistent with existing naming conventions and naming patterns. Maximum 64 characters. Lowercase letters, numbers, and hyphens only. Must not contain XML tags. |
| `description` | Yes | A dense, AI-addressed description of the prompt that captures its high-level intent, context, and primary intended uses. Must be non-empty, must not contain XML tags, and must not exceed 1024 characters. |
| `when_to_use` | No | Additional AI-addressed activation context describing when the prompt should be used, such as trigger phrases, typical user requests, or usage conditions. Use a single string value. Combined with `description`, this field is hard-capped at 1536 characters. |
| `arguments` | No | The expected prompt arguments as an `argument: description` mapping, where each description should function as a compact input contract by clarifying the argument’s role, expected specificity, whether it is required, optional, or contextually required, and any constraints, suggestions, or selection affordances relevant to how it should be supplied. |
| `argument-hint` | If `arguments` is present | A condensed, argument-oriented guidance string that mirrors the semantic input structure defined in `arguments` at a higher level. If `arguments` is specified, `argument-hint` should also be provided to reflect the same expected input logic in a more compact form. |
| `tools` | No | A list of allowed tool or tool set names, expressed as one string value per list item. |
| `status` | Yes | The current working state of the prompt. Allowed values: `concept`, `draft`, `approved`. |
| `category` | No | The canonical thematic grouping or classification of the prompt, expressed as a single string value. See the category index for allowed values. |

## Conventions

- One file per prompt
- Use the `.prompt.md` extension for every prompt file
- The file name must match `name` without the `.prompt.md` extension
- Keep `description` dense, clear, and practically informative
- Keep prompt content operational, concise, and directly usable

## Creating a new prompt

1. Create a new file under `prompts/`
2. Use the `.prompt.md` extension
3. Add the required frontmatter
4. Structure the prompt clearly in Markdown
5. Commit the prompt file

## Example

```text
prompts/example-prompt.prompt.md
```

## Goal

The repository should remain a simple, clean prompt library rather than turning into a chaotic dumping ground for half-finished prompt fragments.

<!-- AI-NOTE: Additional sections are still required and should be added below to further specify prompt authoring guidance, category indexing, validation rules, and related repository conventions. -->

---