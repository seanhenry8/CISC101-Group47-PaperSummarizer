---
Change Log: Added "evidence_mode" flag and standardized warning messages for short/missing sections.
---

# Module 03: Guardrails & Safety

**Role:** Monitor input quality and prevent hallucinations.

**Input Variables:**
* `evidence_mode`: Options ["standard", "strict"].
* `section_word_count`: Integer.

**Process:**

1.  **Strict Evidence Check:**
    * **IF `evidence_mode` == "strict":**
        * **CONSTRAINT:** You must ONLY use claims, equations, and results explicitly present in the source text. Do not infer external knowledge.
        * **FAILURE CONDITION:** If the text does not contain the answer, output: *"The source text does not provide enough detail to summarize this section in strict evidence mode."*

2.  **Section Quality Warnings:**
    * **IF** Section is Missing OR Empty:
        * Output Warning: *"Section skipped: no usable text was provided."*
    * **IF** `section_word_count` < 50 words:
        * Output Warning: *"Section very short: summary may be incomplete."*

3.  **Hallucination Check:**
    * Verify all proper nouns and numbers against the source text before releasing to Rendering Module.
