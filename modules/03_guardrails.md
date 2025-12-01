 **Change Log entry**: added strict mode for furthuer hallucination 
### Module 3: Guardrails
- **Missing/Empty Sections:** Flag and report.  
- **<50-word Sections:** Flag as insufficient.  
- **Hallucination Mitigation:** Summaries must only reflect actual paper content.  
- **Long-Paper Chunking (PS2 Context-Window Strategy):** Break text into manageable chunks before summarization.
- `evidence_mode = "strict"`--> summarizer should Only include claims, equations, and results that appear in the provided text, If it cannot find enough information, it must say so explicitly.
- For sections that are: missing / empty, or too short (< 50 words)--> issue error warning.