# Module Purpose
**Goal:** For each requested section, extract content, validate presence/length, generate audience-appropriate summaries within limits, and produce per-section glossaries.

# Inputs and Outputs
## Inputs
- Normalized section map  
- Preferences object  
- Chunking plan  

## Outputs
- Per-section summaries (expert and lay variants)  
- Per-section mini-glossaries  
- Per-section word counts  
- Section status flags  

# Step-by-Step Logic

## 1. Iterate Sections in Specified Order

### Extraction
- Retrieve text span for each section.  
- If chunked, aggregate the relevant section chunks.

### Validation
- Verify section presence.  
- Check word count.

## 2. Summary Generation

### Core Elements
- Purpose  
- Methods  
- Key results  
- Limitations (when applicable)

### Compression
- Obey word limit per section.
- Preserve only salient, source-supported facts.

### Audience Tone
- **Expert:** Use technical terms, metrics, assumptions, methods, and limitations.  
- **Lay:** Use plain language, minimal jargon, analogies, and outcome-focused framing.

## 3. Mini-Glossary Creation
- **Term selection:** Choose 3–8 key terms per section.  
- **Definitions:** 2–20 words each, derived only from source context.

## 4. Formatting Consistency
- Use consistent headers and bullet structure across sections.  
- Include word counts for each section.

## 5. Status Flags
- **Missing:** Flag and record for downstream processing.  
- **Short (<50 words):** Flag and produce minimal summary.

# Error Handling Procedures
- **Missing section:** Output placeholder summary (“Not available”) and set flag.  
- **Short section:** Generate minimal possible summary and issue a warning.  
- **Over-limit text:** Trim carefully while retaining meaning; report final word count.
