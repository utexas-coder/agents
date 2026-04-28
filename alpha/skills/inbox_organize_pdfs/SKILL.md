---
name: inbox_organize_pdfs
description: Process all .pdf files in ~/inbox: move to ~/processed, extract and summarize text, classify into a three-word topic, find/create matching subdirectory in ~/knowledge, and move PDF there.
---

# Inbox Organize PDFs Skill

Automatically processes incoming PDF documents from your inbox directory, extracting content, summarizing, and organizing them into relevant knowledge subdirectories.

## What It Does

When activated, this skill will:

1. **Scan** the `~/inbox` directory for all `.pdf` files
2. **Move** each file to `~/processed` (temp staging)
3. **Extract** text from the PDF using `pdftotext`
4. **Summarize** the extracted content
5. **Classify** with a three-word topic classification (e.g., "Financial Report", "World News", "Technical Doc")
6. **Locate/Create** the closest matching subdirectory in `~/knowledge`
7. **Move** the PDF file into the appropriate knowledge subdirectory
8. **Write** a summary markdown file to the knowledge subdirectory with the PDF

## Classification Examples

- Financial reports → "Financial Report"
- News articles → "World News" or "Sports News"
- Technical documents → "Technical Doc"
- General correspondence → "General Mail"
- Research papers → "Research Paper"
- Meeting minutes → "Meeting Notes"
- Contracts → "Legal Contract"

## Requirements

- `pdftotext` utility installed (comes with poppler-utils on macOS)
- Write permissions to `~/inbox`, `~/processed`, and `~/knowledge` directories

## Usage

Invoke the skill when you want to process incoming PDFs:

```
inbox_organize_pdfs
```

The skill will process all PDF files found in your ~/inbox directory, one by one.

## Workflow

```
~/inbox/*.pdf
    ↓ (move)
~/processed/
    ↓ (pdftotext + summarize)
    ↓ (classify 3-word topic)
    ↓ (find/create matching subdirectory)
~/knowledge/[TOPIC/]/*.pdf
```

## Example

Given these files in `~/inbox`:
- `newsletter_april.pdf`
- `contract_v2.pdf`
- `market_report_2026.pdf`

The skill would:
1. Move all three to `~/processed`
2. Extract and summarize each file's content
3. Classify them (e.g., "Market Report", "Legal Contract", "Newsletter")
4. Find or create matching directories in `~/knowledge`
5. Move each PDF to its appropriate location

Perfect for automatically organizing incoming documents into your knowledge base. 📁
