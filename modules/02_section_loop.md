<!-- file: modules/02_section_loop.md -->
# Section iteration and child-friendly summarization

#### Loop control
- **Initialize:** For each user-requested section, locate its content in the section index.
- **Skip/fallback:** If not found, record as missing and continue; do not invent content.

#### Child-friendly constraint
- **Simple language:** Short sentences, common words, avoid unexplained jargon.
- **Analogy-first:** Use everyday comparisons:
  - **Example:** “The model is like a team of helpers who pass notes to each other to understand a story.”
- **Break down steps:** Explain complex processes in 3–5 simple steps.
- **Highlight purpose:** Clearly state what the section is trying to do (question, method, result).

#### Per-section summary template
- **Core question:** What problem or idea is this section focused on?
- **Simple summary:** 2–5 sentences in child-friendly language.
- **Key details:** 3–5 bullets for important data, methods, or findings.
- **Signals:** Note assumptions, limitations, or special cases present in the text.

#### Output collection
- **Store structured summaries:** Keep per-section objects for rendering:
  - **Fields:** name, core_question, simple_summary, key_details, flags (missing, empty, short)

