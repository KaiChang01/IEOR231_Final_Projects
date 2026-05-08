# raw/ — Source Material

This directory holds all unprocessed source material that feeds the wiki. You drop things in here; the LLM compiles them into articles in `wiki/`.

## What belongs here

- PDFs of FDA guidance documents, ICH guidelines, industry white papers
- Web-clipped articles (use Obsidian Web Clipper → saves as `.md`)
- Notes from training, onboarding, conversations with colleagues
- Screenshots or images of process diagrams, flow charts, org charts
- Textbook excerpts (paste relevant sections as `.txt` or `.md`)

## Naming convention

```
YYYY-MM-DD_source_short-description.ext
```

Examples:
- `2026-05-01_FDA_process-validation-guidance.pdf`
- `2026-05-01_clip_tech-transfer-overview-pharmtech.md`
- `2026-05-04_note_onboarding-day1.md`

## How to trigger a wiki update

Once you've added new files here, ask Claude:

> "I've added new files to raw/. Please compile them into the wiki — update or create relevant articles and refresh `_index.md`."

Claude will read the new source material, extract key concepts, and either create new articles or append/revise existing ones in `wiki/`.

## Current sources

_(empty — add your first source document to get started)_
