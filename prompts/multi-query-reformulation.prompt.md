---
name: multi-query-reformulation
description: "Generates five alternative and one synthesized retrieval-oriented query formulations from an original user question to improve semantic and vector-based document retrieval, optionally adapting terminology from a supplied document."
when_to_use: "Use when a user wants to reformulate an initial question into multiple stronger retrieval queries for RAG, semantic search, vector databases, or document search, especially when the first query is underspecified or when a source document should inform terminology."
arguments:
  original_question: "The user's initial question to be rewritten into five alternative retrieval-oriented queries and one synthesized query; required."
  supplied_document: "Optional attached or pasted document whose domain terminology, themes, and central concepts should be analyzed and reflected in the generated queries when present."
argument-hint: "Provide the original question; optionally include a source document so the rewritten retrieval queries can inherit its terminology and domain framing."
status: draft
category: query-engine
---

Your task is now to generate five slightly different versions of the given user question to retrieve relevant documents from a modern vector database. By generating multiple perspectives on this original question, your goal is to help the user overcome some of the limitations of initial, poorly crafted queries used for distance-based similarity search retrieval.

So here is my original question:
<original_question>
{{original_question}}
</original_question>

Construct these alternative, narrowly focused yet comprehensive natural-language queries, optimized for modern LLM document-retrieval methods.

Provide only output as follows:
1. Five separate code blocks (one per alternative query), numbered in order and separated by ONE EMPTY LINE, in the following format:

   ```text
   Query <n>: <alternative query>?
   ```

2. One additional code block containing a synthesis of all five queries and the following usage note (enclosed in quotation marks), in this format:

   ```text
   Query: <coherent natural-language query>?
   "Usage note: If the user responds in a follow-up turn with one of the proposed queries above, that query will be treated as the active query input and used directly for document retrieval."
   ```

3. Close your response with a numbered list of multiple-choice options for further retrieval paths for which there is sufficient confidence that they may yield relevant and useful next results, also taking into account what the user might not have considered yet.


**Document handling instructions:** When a document is supplied or attached, you must analyze it thoroughly, identify its context and domain, and use its key terminology and central themes to craft relevant alternative queries. Maintain the mapping between the proposed queries and subsequent follow-up turns. In the case of a supplied document, you must state the following explicitly: "If the user responds in a follow-up turn with one of the proposed queries above, that query will be treated as the active query input and used directly for document retrieval."