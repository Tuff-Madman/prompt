# Repository instructions

Follow these instructions when creating, editing, retrieving, applying, validating, or maintaining reusable prompt files in this repository, as specified below.

## Prompt file format and structure

Maintain each prompt as a Markdown prompt file with the strictly required `.prompt.md` extension.

Pattern for prompt files: `prompts/<prompt-name>.prompt.md`.

Create each prompt file with a required YAML frontmatter metadata block followed by a Markdown body containing the prompt itself.

### Frontmatter schema

The frontmatter defines the prompt's identity, high-level intent, activation context, input expectations, allowed tools, lifecycle state, and category assignment.

| Field | Required | Description |
|---|---|---|
| `name` | Yes | The name of the prompt. Must exactly match the file name without the `.prompt.md` extension. Use an ontologically consistent, kebab-case name with hyphens, consistent with existing naming conventions and naming patterns. Maximum 64 characters. Lowercase letters, numbers, and hyphens only. Must not contain XML tags. |
| `description` | Yes | A dense, AI-addressed description of the prompt that captures its high-level intent, context, and primary intended uses. Must be non-empty, must not contain XML tags, and must not exceed 1024 characters. |
| `when_to_use` | No | Additional AI-addressed activation context describing when the prompt should be used, such as trigger phrases, typical user requests, or usage conditions. Use a single string value. Combined with `description`, this field is hard-capped at 1536 characters. |
| `arguments` | No | The expected prompt arguments as an `argument: description` mapping, where each description should function as a compact input contract by clarifying the argument’s role, expected specificity, whether it is required, optional, or contextually required, and any constraints, suggestions, or selection affordances relevant to how it should be supplied. |
| `argument-hint` | If `arguments` is present | A condensed, argument-oriented guidance string that mirrors the semantic input structure defined in `arguments` at a higher level. If `arguments` is specified, `argument-hint` should also be provided to reflect the same expected input logic in a more compact form. |
| `tools` | No | A list of allowed tool or tool set names, expressed as a YAML block list with one string value per list item. |
| `status` | Yes | The current working state of the prompt. Allowed values: `concept`, `draft`, `approved`. |
| `category` | No | The canonical thematic grouping or classification of the prompt, expressed as a single string value. See the category index for allowed values. |

### Category index schema

The category index is maintained in `data/categories.yml`.

The category index defines the canonical registry of allowed prompt categories. It is AI-addressed and optimized for stable prompt classification, retrieval, disambiguation, and taxonomy-aware organization.

| Field | Required | Description |
|---|---|---|
| `name` | Yes | The canonical category key. Must be unique, stable, and expressed in kebab-case using lowercase letters, numbers, and hyphens only. This value is the authoritative reference target for `category` in prompt frontmatter. |
| `description` | Yes | A dense AI-addressed semantic scope definition of the category. It defines the category’s intended meaning, primary inclusion boundary, and practical distinction from nearby or potentially confusable categories. It is optimized for interpretive precision, classification usefulness, and retrieval relevance rather than stylistic readability. |
| `parent` | No | The canonical `name` of the direct parent category. This field is used only for subcategories and omitted for root categories. It defines taxonomy structure inside the category index and must not be used as an additional prompt-level category assignment. |

### Prompt body formatting and authoring standards

If a prompt uses arguments, the body must include placeholders delimited by double curly braces, e.g. `{{argument}}`, exactly matching the keys declared under `arguments`.

- Argument hints: Each argument should be understandable by its hint alone, which specifies whether it is required, plus any defaults, options, necessary instructions, constraints, and usage details.

- Argument references: One consistent style should be used for any prompt-body reference that exactly matches an argument key and is outside placeholders or XML tags:
  - If a clearly recognizable argument-reference style is already established (e.g. uppercase, camelCase, snake_case, quoted, or backtick references), preserve it consistently wherever it applies.
  - Otherwise, use backtick references such as `argument`.

- Long-form arguments: Unless otherwise specified, argument values spanning multiple lines should be treated as long-form arguments and wrapped in semantic XML-style tags following the inline structure `<argument>\n{{argument}}\n</argument>`, where `\n` denotes a line break in the prompt body, not literal text.
  - Continuation phrase: Additionally, include a continuation-style phrase such as `"... wrapped in <argument> tags above/below/in the relevant section/under the relevant heading."`, where the leading `...` means the phrase should be attached organically to the first or most relevant existing mention or reference to that argument within the prompt body when possible.

## Conventions

- Create one file per prompt
- Use the `.prompt.md` extension for every prompt file
- Ensure the file name matches `name` without the `.prompt.md` extension
- Keep `description` dense, clear, and practically informative
- Treat user-provided prompt content as verbatim by default. Only fix obvious mechanical typos or spelling mistakes with exactly one plausible correction; otherwise preserve the original and flag the issue.
- When authoring new prompt content, keep it operational, concise, and directly usable.

## Workflows

### Creating a new prompt

1. Create a new file under `prompts/`
2. Use the `.prompt.md` extension
3. Add the required frontmatter
4. If setting `category`, follow the “Assigning or creating categories” workflow below.
5. Structure the prompt clearly in Markdown
6. Commit the prompt file

### Assigning or creating categories

1. Check `data/categories.yml` before assigning a category.
2. Compare the prompt’s purpose against existing category names, descriptions, and parent relationships.
3. Use an existing category when it clearly fits.
4. If no existing category fits, propose a new category and explain why existing categories are insufficient.
5. Create a new category only after user confirmation.

## Validation checklist

- Ensure each prompt file uses the `.prompt.md` extension.
- Ensure frontmatter `name` matches the filename without `.prompt.md`.
- Ensure required frontmatter fields are present: `name`, `description`, and `status`.
- Ensure `argument-hint` is present whenever `arguments` is present.
- If `arguments` is declared or argument usage is clearly implied, verify a correct `arguments` definition (and its mirroring `argument-hint`), the existence of matching `{{argument}}` placeholders, and strict adherence to the applicable “Prompt body formatting and authoring standards”.
- Verify that any assigned `category` exists in `data/categories.yml` or was created after user-confirmed category review.
- Preserve user-provided prompt content according to the verbatim-by-default convention.

## Note

The goal is to keep the repository a simple, clean prompt library rather than turning it into a chaotic dumping ground for half-finished prompt fragments.

To preserve that goal, interpret and apply these instructions flexibly according to the current user request, retrieval or application context, and relevant repository state, without weakening required file-format, frontmatter, category, or confirmation rules.

<!-- AI-NOTE: Additional sections are still required and should be added below to further specify prompt authoring guidance, category indexing, validation rules, and related repository conventions. -->

---