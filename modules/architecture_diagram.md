# Text-Based Flow

## Module 1: Intake & Setup
- **Receives:** Paper file, sections, audience, limits, format  
- **Produces:** Normalized sections, existence/short reports, preferences, chunking plan  
- **Flows to:** Module 2 (Section Loop), Module 5 (Citation Extractor)  

## Module 2: Section Loop
- **Receives:** Normalized sections, preferences, chunking plan  
- **Produces:** Per-section summaries (expert/lay), glossaries, word counts, status flags  
- **Flows to:** Module 3 (Guardrails), Module 4 (Rendering & Refinement)  

## Module 3: Guardrails
- **Receives:** Section outputs, status flags, chunking plan, citation data  
- **Produces:** Validated summaries, Checks & Warnings, citation verification status  
- **Flows to:** Module 4 (Rendering & Refinement)  

## Module 4: Rendering & Refinement
- **Receives:** Validated summaries, glossaries, counts, citation registry, warnings  
- **Produces:** Final document with required sections and consistent formatting  
- **Outputs:** Paper Summary, Section-by-Section Table, Expert Summary, Lay Summary, Mini-Glossary, Checks & Warnings  

## Module 5: Citation Extractor
- **Receives:** Paper text, section boundaries  
- **Produces:** Citation registry by section, formatted citation lists, per-section counts  
- **Flows to:** Module 3 (Guardrails), Module 4 (Rendering & Refinement)  

## Module 6: Key Contributions Summarizer
- **Receives:** Section texts and entire paper context as needed  
- **Produces:** 3–5 contributions bullets linked to sections  
- **Flows to:** Module 4 (Rendering & Refinement); optionally referenced in Expert/Lay summaries
