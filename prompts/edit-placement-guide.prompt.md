---
name: edit-placement-guide
description: Creates a numbered placement guide that maps recommended edits to exact document locations, including edit description, required action, and precise placement anchors.
when_to_use: Use when recommended edits need to be converted into a precise numbered placement guide for applying changes to a document by section, paragraph, line number, heading, theorem, or anchor text.
arguments:
  recommended_edits: Required. The concrete edits, reviewer comments, suggested changes, or revision requests that must be placed into the target document. Each item should be specific enough to identify what needs to change, but may be unresolved, unordered, or not yet tied to a location.
  target_document: Contextually required. The full document, excerpt, outline, or numbered text used to identify reliable placement anchors such as headings, sections, paragraphs, line numbers, theorem labels, table captions, figure references, or exact quoted text.
  additional_edit_specification: Optional. Extra constraints that affect placement logic or output shape, such as preferred action labels, required granularity, ordering rules, fallback behavior when exact line numbers are missing, or whether uncertain placements should be flagged.
argument-hint: Provide the recommended edits plus the target document or excerpt; optionally add constraints for placement precision, action labels, ordering, fallback anchors, and uncertainty handling.
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
