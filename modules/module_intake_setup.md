# Module Purpose
**Goal:** Validate inputs, normalize section names, detect missing or short sections, and store user preferences to guide downstream modules.

# Inputs and Outputs
## Inputs
- Paper file (PDF or text)
- Requested sections list
- Target audience
- Word limit per section (default: 100)
- Format preferences
- Global page limit

## Outputs
- Normalized section map  
- Section existence report  
- Short-section report (<50 words)  
- Stored preferences object  
- Chunking plan (if >10 pages)

# Step-by-Step Logic

## 1. Validate Inputs
### File check
- Confirm readable text.
- Attempt text extraction if PDF is provided.

### Preferences
- Load audience, word limit, format preferences, and page limit.
- Assign defaults if values are missing.

## 2. Normalize Section Names
### Mapping
- Convert variant names to canonical forms:  
  - *Intro → Introduction*  
  - *Methodology → Methods*  
  - *Results & Analysis → Results*

### Order
- Follow user-specified ordering.
- If none provided, use canonical order.

## 3. Section Boundary Detection
### Headings parse
- Identify section headings and their text spans.

### Map creation
- Build:  
  `{ section_name: text_span, word_count }`

## 4. Detect Missing/Short Content
### Missing
- Mark sections not found in the parsed text.

### Short
- Flag any section with fewer than 50 words.

## 5. Chunking Plan (Context Management)
- Apply when paper exceeds 10 pages.
- Segment by section and/or page ranges.
- Keep references separate from main sections.

## 6. Store Preferences
- **Audience:** Expert / Layperson / General  
- **Limits:** Word-per-section; global page limit  
- **Format:** Tables, headings, bullets  

# Error Handling Procedures
- **Unreadable file:** Return error flag and message; suggest uploading text-based content.
- **No sections detected:** Return warning; request section list or default to canonical sections.
- **Ambiguous headings:** Use best-match normalization and flag ambiguity in *Checks & Warnings*.
- **Short sections:** Record in short-section report for Module 3 Guardrails.
