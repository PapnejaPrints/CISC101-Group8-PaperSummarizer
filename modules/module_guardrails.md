# GitHub Change Log
- **Date:** 2025-11-28  
- **Changes:**  
  - Added `evidence_mode` variable to enable "strict" evidence mode.  
  - Standardized warning messages for missing or very short sections:  
    - “Section skipped: no usable text was provided.”  
    - “Section very short: summary may be incomplete.”  

# Module Purpose
**Goal:** Enforce safety and integrity by handling missing/empty sections, warning on short content, preventing hallucinations, managing context windows, and verifying citations.

# Inputs and Outputs
## Inputs
- Section status flags  
- Per-section outputs  
- Chunking plan  
- Extracted citations  
- **Evidence mode** (`evidence_mode`) – optional, e.g., `"strict"`

## Outputs
- Checks & Warnings report  
- Validated summaries  
- Citation verification status  

# Step-by-Step Logic

## 1. Missing/Empty Section Handler
- **Action:** Replace summary with *“Section not found in source”*.  
- **Warning message:** “Section skipped: no usable text was provided.”  
- Add entry to global warnings list.

## 2. Short Section Warning
- **Threshold:** <50 words.  
- **Warning message:** “Section very short: summary may be incomplete.”  
- Append a section-level warning and record in global report.
- If section is missing, empty or has less than 50 words, display a warning message stating “section summary may be incomplete”


## 3. Hallucination Prevention / Strict Evidence Mode
- **Rule:** Disallow any content not present in the source text.  
- **Strict Evidence Mode (`evidence_mode = "strict"`):**  
  - Only include claims, equations, and results that appear in the provided text.  
  - If insufficient information is found, explicitly state:  
    *“The source text does not provide enough detail to summarize this section in strict evidence mode.”*  
- **Scan:** Compare each summary’s claims against its corresponding text span.  
- Reject external or speculative facts.
- If (evidence_mode = "strict", then only include text, equations, and results that explicitly appear in the provided paper.

## 4. Context Window Management
- **Chunking:** Process sections iteratively to avoid cross-section contamination.  
- **Memory:** Retain only section-local context; clear after output is generated.

## 5. Citation Verification
- **Check:** Confirm all citations originate from the extracted references or in-text citations.  
- **Reject:** Remove invented references and mark mismatches.

# Error Handling Procedures
- **Verification failure:** Mark section as unverifiable and add warning.  
- **Chunking overflow:** Reduce chunk size; prioritize section boundaries.  
- **Ambiguous content:** Label as ambiguous and avoid speculative interpretation.  
- **Strict Evidence Mode gaps:** Output explicit message if section cannot be summarized due to lack of evidence.
