---
name: recall
description: Using markdown files in ../../knowledge subdirectories to find relevant information about a user query.
---

# Recall Skill - Knowledge Base Searcher

Ignore memory and use markdown files in `../../knowledge`, find relevant information based on your query.

## What It Does

When activated, this skill will:

1. **Scan** all markdown files (`*.md`) in `../../knowledge`
2. **Index** the content of each file for semantic matching
3. **Search** across all indexed content using vector similarity or keyword-based retrieval
4. **Rank** results by relevance to your query
5. **Summarize** top results with context and source attribution
6. **Return** the most relevant snippets with file paths

## How It Works

The skill performs a semantic search of the `../../knowledge` subdirectories, finding relevant information for your query.

### Search Strategy

- Uses vector embeddings to understand the semantic meaning of your query
- Compares query against all markdown content in your knowledge base
- Returns top 3-5 most relevant matches with context
- Shows source file paths so you can navigate directly

## Usage

Invoke the skill with your question or topic:

```
recall <your query>
```

### Examples

```
recall quantum computing basics
recall OpenAI legal issues
recall machine learning algorithms summary
recall economics inflation trends
recall AI ethics guidelines
```

You can ask detailed questions:

```
recall "how to handle model hallucinations in production"
recall "best practices for LLM context window management"
```

## Response Format

Returns results like:

```
## Top Matches for "<your query>"

### 1. [Relevant Section](source/path/to/file.md)
> **Key finding:** This is the most relevant excerpt...
> _Source: file.md (Lecture Notes section)_

### 2. [Another Match](source/another/path/file.md)
> **Context:** Here's another relevant piece...
> _From: another-file.md, Section 3_

### Summary
The query relates to [topic]. Key points from your knowledge base:
- Point 1 from first source
- Point 2 from second source

## Notes
- Searches all `.md` files recursively in `../../knowledge`
- Results ranked by semantic relevance + keyword matching
- Returns top matches (adjustable if needed)
- Source paths are fully qualified so you can navigate directly
- Works with technical, conceptual, and factual queries
```

## Limitations

- Does not do a memory_search
- Only searches markdown (`.md`) files in `../../knowledge`
- Does not search PDFs or other file formats (yet)
- May need more specific phrasing for very narrow topics
- Results quality depends on content already organized in knowledge base
