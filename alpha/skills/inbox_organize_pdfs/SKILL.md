---
name: inbox_organize_pdfs
description: Process all .pdf files in ../../inbox: move to a new subdirectory in ../../processed, extract and summarize text, classify into a three-word topic, find/create matching subdirectory in ../../knowledge, and move PDF there.
---

# Inbox Organize PDFs Skill

Automatically processes incoming PDF documents from your inbox directory, extracting content, summarizing, and organizing them into relevant knowledge subdirectories.

## What It Does

When activated, this skill will:

1. **Create** a new `../../processed` subdirectory named based on the date and time
2. **Scan** the `../../inbox` directory for all `.pdf` files
3. **Move** each file to the new `../../processed` subdirectory
4. **Extract** text from the PDF using `pdftotext`
5. **Summarize** and extract key-points from the extracted text
6. **Classify** with a three-word topic classification (e.g., "Financial Report", "World News", "Technical Doc")
7. **Locate/Create** the closest matching subdirectory in `../../knowledge`
8. **Write** key-points to a markdown file in appropriate `../../knowledge` subdirectory
9. **Move** the PDF to the appropriate `../../knowledge` subdirectory

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
- Write permissions to `../../inbox`, `../../processed`, and `../../knowledge` directories

## Usage

Invoke the skill when you want to process incoming PDFs:

```
inbox_organize_pdfs
```

The skill will process all PDF files found in your ../../inbox directory, one by one.

## Notes
- Works with image-based PDFs (no pdftotext dependency)
- Classification based on filename keywords and topic analysis
- Each processed PDF gets a summary markdown in its target directory
