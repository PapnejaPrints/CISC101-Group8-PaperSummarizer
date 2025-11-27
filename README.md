# CISC101-Group8-PaperSummarizer

## Group Members 
- Jasnoor Kang 
- Rahul Manjangal Narayanan 
- Brahmleen Papneja 

--- 

## Repository Components 

This repository contains the complete Research Paper Summarizer system developed for CISC 101 Week 10 Tutorial. 

### Files: 

- **system_prompt.md** - The main system prompt that defines the AI's behavior, greeting rules, required inputs, boundaries, safety rules, and output structure for the Research Paper Summarizer. 

- **modules/** - Internal reference framework containing six modular components: 

- `01_intake_and_setup.md` - Validates inputs, normalizes section names, detects missing/short sections, creates chunking plans 
- `02_section_loop.md` - Iterates through sections to generate summaries with audience-appropriate tone and mini-glossaries 
- `03_guardrails.md` - Enforces hallucination prevention, handles missing/empty sections, manages context windows, verifies citations 
- `04_rendering_and_refinement.md` - Assembles final document with consistent formatting, expert/lay variants, and checks & warnings 
- `05_citation_extractor.md` - Extracts and organizes citations per section with standardized formatting 
- `06_key_contributions_summarizer.md` - Identifies 3-5 key innovations and links them to source sections 

--- 

## Project Overview 

The Research Paper Summarizer is designed to generate accurate, audience-appropriate summaries of research papers. It incorporates: 

- **Specification Design** - Clear inputs (paper, sections, audience, limits, format), outputs (summaries, glossaries), and constraints (word/page limits, section order) 
- **Test-Driven Development** - Iterative refinement based on test oracles to ensure output quality 
- **Modular Architecture** - Six reusable components with defined responsibilities and clear data flow 
- **Safety Guardrails** - Strict hallucination prevention, missing-section handling, and citation verification 
- **Dual Audience Support** - Both expert (technical, precise) and lay (plain-language, analogies) summary variants 
- **Context Management** - Chunking strategies for papers exceeding 10 pages 

--- 

## System Features 

The system prompt and modules work together to process research papers and generate structured summaries that include: 

- **Paper Summary** - Brief 2-4 sentence overview of the entire paper 
- **Section-by-Section Table** - Organized summaries for each requested section with word counts and citation counts 
- **Expert Summary** - Technical language for researchers with methodology, metrics, and limitations 
- **Lay Summary** - Plain-language explanation using analogies and everyday terms 
- **Per-Section Mini-Glossaries** - Key technical terms (3-8 per section) with concise definitions
- **Citation Analysis** - Extracted citations organized by section with counts 
- **Key Contributions** - 3-5 main innovations linked to source sections 
- **Checks & Warnings** - Comprehensive report of missing sections, short sections, and formatting issues 
--- 

## Design Principles 

- **Source Fidelity** - Only summarize content explicitly present in the paper; no hallucinations
- **Audience Adaptation** - Adjust tone and detail level without altering factual content 
- **Constraint Enforcement** - Strict adherence to word/page limits with intelligent compression 
- **Transparency** - Clear reporting of limitations, missing content, and processing issues 
- **Modularity** - Reusable components with well-defined inputs, outputs, and error handling
