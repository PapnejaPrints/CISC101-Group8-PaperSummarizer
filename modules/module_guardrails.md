# Module Purpose
**Goal:** Enforce safety and integrity by handling missing/empty sections, warning on short content, preventing hallucinations, managing context windows, and verifying citations.

# Inputs and Outputs
## Inputs
- Section status flags  
- Per-section outputs  
- Chunking plan  
- Extracted citations  

## Outputs
- Checks & Warnings report  
- Validated summaries  
- Citation verification status  

# Step-by-Step Logic

## 1. Missing/Empty Section Handler
- **Action:** Replace summary with *“Section not found in source”*.  
- Add entry to global warnings list.

## 2. Short Section Warning
- **Threshold:** <50 words.  
- Append a section-level warning and record in global report.

## 3. Hallucination Prevention
- **Rule:** Disallow any content not present in the source text.  
- **Scan:** Compare each summary’s claims against its corresponding text span.  
- Reject external or speculative facts.

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
