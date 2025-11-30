# CISC101-Group24PaperSummarizer
# Research Paper Summarizer — PS2 Specification (Week 10)

## Overview
This repository contains the **system prompt** and internal architecture for a **Research Paper Summarizer** designed to process academic papers with precision and rigor.  
It integrates the **PS2 Summarizer Specification (Week 10)** and provides a modular framework for summarizing research papers section-by-section, extracting citations, and identifying key contributions.

---

## Features
- 📑 **Section-by-Section Summarization**  
  Summarizes each section of a paper in ≤150 words, following the original order.

- 🧠 **Unified Paper Summary**  
  Combines all section summaries into a cohesive final summary.

- 🎓 **Expert & Lay Summaries**  
  Produces both technical (expert) and simplified (layperson) summaries.

- 📚 **Mini-Glossary**  
  Defines key technical terms for accessibility.

- ⚠️ **Checks & Warnings**  
  Flags missing sections, short sections (<50 words), and constraint violations.

- 🔍 **Citation Extractor**  
  Extracts all in-text citations, preserving order and formatting.

- 🌟 **Key Contributions Summarizer**  
  Identifies explicit contributions per section and highlights the paper’s most important contributions.

---

## PS2 Summarizer Specification

| Category   | Description                                                                 |
|------------|-----------------------------------------------------------------------------|
| Inputs     | Paper title = "Attention Is All You Need"<br>Paper text = full PDF<br>Link = https://arxiv.org/pdf/1706.03762<br>Section headings (e.g., Introduction, Model Architecture, Results) |
| Outputs    | • Individual summary for each section<br>• Final unified summary combining all section summaries |
| Constraints| • Section summaries must follow original order<br>• ≤150 words per section<br>• Formal academic tone with consistent terminology |

---

## Internal Architecture

### Module 1: Intake & Setup
- Normalize section headings
- Detect missing or short sections
- Prepare metadata (title, link, section list)

### Module 2: Section Loop
- Summarize each section (≤150 words)
- Maintain academic tone
- Verify section order

### Module 3: Guardrails
- Flag missing/empty sections
- Warn if <50 words
- Prevent hallucinations
- Apply PS2 context-window strategies for long papers

### Module 4: Rendering & Refinement
- Assemble unified summary
- Format consistently
- Generate expert & lay summaries

### Module 5: Citation Extractor
- Extract all in-text citations
- Preserve order and formatting
- Output structured citation list

### Module 6: Key Contributions Summarizer
- Extract contributions per section
- Identify most important contributions
- No hallucinations; only evidence-supported contributions

---

## Output Format
- **Markdown-based structure** for clarity
- **Tables** for section summaries
- **Separate labeled sections** for Expert vs Lay summaries
- **Bullet points** for glossary
- **Lists** for checks & warnings

---

## Example Output Skeleton

### Paper Summary
*(Unified summary here)*

### Section-by-Section Table
| Section        | Summary (≤150 words) |
|----------------|-----------------------|
| Introduction   | ...                   |
| Model Arch.    | ...                   |
| Results        | ...                   |

### Expert Summary
*(Technical, formal summary)*

### Lay Summary
*(Simplified, accessible summary)*

### Mini-Glossary
- **Transformer**: Definition  
- **Attention**: Definition  
- **Encoder-Decoder**: Definition  

### Checks & Warnings
- Missing sections: ...  
- Short sections: ...  
- Constraint violations: ...  

### Citation Extractor
- [Vaswani et al., 2017]  
- [Bahdanau et al., 2015]  
- [Luong et al., 2015]  

### Key Contributions Summarizer
- Introduction: Contribution list  
- Model Architecture: Contribution list  
- Results: Contribution list  
- Overall: Most important contributions  

---

## Usage
1. Provide the paper PDF and section headings.  
2. Run the summarizer through the defined modules.  
3. Review outputs: section summaries, unified summary, glossary, citations, contributions.  
4. Validate against constraints (≤150 words, formal tone, no hallucinations).  

---

## License
This repository is released under the **MIT License**.  
You are free to use, modify, and distribute with attribution.

---

