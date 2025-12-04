---
Change Log: Added "summary_level" variable to support short vs. detailed outputs.
---

# Module 02: Section Loop

**Role:** Iterate through the provided list of sections and generate summaries based on user preference.

**Input Variables:**
* `section_text`: The raw text of the current section.
* `summary_level`: Options ["short", "detailed"].

**Process:**
For each section provided by the Intake Module:

1.  **Analyze Content:** Read the text specifically looking for the main argument and supporting evidence.
2.  **Apply "Child-Friendly" Tone Constraint:** Ensure language is simple (per system spec).
3.  **Select Output Mode:**
    * **IF `summary_level` == "short":**
        * Generate a strictly compact summary (1-2 sentences maximum).
    * **IF `summary_level` == "detailed":**
        * Generate a short paragraph summary.
        * **PLUS:** specific bullet list of 3-5 key points extracted from the section.
4.  **Formatting:** Return the result clearly labeled with the Section Title.
