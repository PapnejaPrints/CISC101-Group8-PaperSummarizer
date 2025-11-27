# Module Purpose
**Goal:** Assemble the final summary document with consistent formatting, produce expert and lay variants, integrate glossaries, and append checks and warnings.

# Inputs and Outputs
## Inputs
- Per-section summaries (expert and lay)  
- Per-section glossaries  
- Word counts and citation counts  
- Citation data  
- Warnings  

## Outputs
- Final summary document containing all required sections, formatted according to user preferences  

# Step-by-Step Logic

## 1. Assemble Paper Summary
- **Scope:** 2–4 sentences covering objective, method, findings, and implications.

## 2. Render Section-by-Section Table
- **Columns:** Section, Summary (expert), Summary (lay), Word count, Citations count  
- **Order:** Follow user-specified order or canonical order

## 3. Expert Summary (Global)
- **Content:** Methods, datasets, metrics, results, limitations, future work

## 4. Lay Summary (Global)
- **Content:** Plain-language overview; answer *“what, how, why it matters”*

## 5. Mini-Glossary (Per-Section)
- **Format:** Bulleted lists with short definitions (2–20 words)

## 6. Checks & Warnings
- **Items to include:** Missing sections, short sections, unreadable text, citation issues, formatting anomalies

## 7. Refinement
- **Consistency:** Apply headings, bullets, table schema uniformly  
- **Limits:** Confirm word/page limits; trim if necessary  
- **Counts:** Include word counts and citation counts

# Error Handling Procedures
- **Formatting conflict:** Default to canonical format; note issue in warnings  
- **Exceeded limits:** Compress summaries by prioritizing: objective > method > key results > limitations  
- **Glossary gaps:** If insufficient terms, indicate minimal glossary availability
