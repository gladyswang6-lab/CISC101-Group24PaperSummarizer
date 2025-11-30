 **Change Log entry**: added strict mode for furthuer hallucination mitigation. 
 ### Module 3: Guardrails
- **Missing/Empty Sections**: Issue warnings.
- **Short Sections (<50 words)**: Flag for review.
- **Hallucination Mitigation**: Summaries must remain faithful to source text.
- **Long-Paper Chunking**: Apply PS2 context-window strategies to handle extended text.
- `evidence_mode = "strict"`--> summarizer should Only include claims, equations, and results that appear in the provided text, If it cannot find enough information, it must say so explicitly.
- For sections that are: missing / empty, or too short (< 50 words)--> issue error warning.
