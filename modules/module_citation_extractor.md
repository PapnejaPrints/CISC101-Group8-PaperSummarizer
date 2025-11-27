# Module Purpose
**Goal:** Extract all citations from the paper, organize by section, format consistently, and provide citation counts per section.

# Inputs and Outputs
## Inputs
- Paper text  
- Section boundaries  

## Outputs
- Citation registry by section  
- Formatted citation list  
- Per-section citation counts  

# Step-by-Step Logic

## 1. Identify Citation Forms
- **Patterns:** In-text (e.g., “(Smith, 2020)”), numeric [1], superscripts, footnotes, references list

## 2. Extract References Section
- **Parse:** Collect full bibliographic entries from the references section

## 3. Map In-Text Citations to References
- **Linking:** Associate numeric or author-year keys to full reference entries

## 4. Organize by Section
- **Registry:** `{ section_name: [citations] }` with counts per section

## 5. Format Output
- **Consistency:** Use author-year or numeric style matching the paper  
- **Counts:** Include total citations per section  
- **Note:** Do not invent missing fields

# Error Handling Procedures
- **Unlinked citations:** Mark as *“unresolved”* and add to warnings  
- **Non-standard formats:** Attempt best-effort pattern matching; flag anomalies  
- **No references section:** Provide in-text citation list only; issue warning about missing bibliography
