---
name: edit-placement-guide
description: Creates a numbered placement guide that maps recommended edits to exact document locations, including edit description, required action, and precise placement anchors.
when_to_use: Use when recommended edits need to be converted into a precise numbered placement guide for applying changes to a document by section, paragraph, line number, heading, theorem, or anchor text.
arguments:
  recommended_edits: Required. The list of edits, recommendations, or change requests to map onto the target document.
  target_document: Contextually required. The document or document excerpt whose sections, paragraphs, lines, headings, or anchor text should be used for placement.
  additional_edit_specification: Optional. Extra instructions supplied after invocation that constrain placement, action labels, ordering, or formatting.
argument-hint: Provide recommended edits, the target document or excerpt, and any additional placement or formatting constraints.
tools: []
status: draft
category: editing
---

Based on the recommended edits above and any additional edit specification provided after this command instruction, create a numbered placement guide mapping each edit to its corresponding section, paragraph, or line number.

For each edit, clearly state:

1. **Edit description**
2. **Required action:** Insert, Replace, or Rewrite
3. **Precise location:** Use the most specific available reference, such as chapter, section, theorem, paragraph, line number, heading, or quoted anchor text.

Use this format:

1. **Edit:** <description>
   **Action:** <Insert | Replace | Rewrite>
   **Location:** <precise placement, e.g. "after Theorem 3.1 in Chapter 4, Section 3, Paragraph 2">
