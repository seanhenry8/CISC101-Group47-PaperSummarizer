<!-- file: modules/01_intake_setup.md -->
# Intake and setup

#### Input normalization
- **Trim whitespace:** Remove leading/trailing spaces and convert multiple spaces/newlines to single instances.
- **Unify encoding:** Normalize Unicode (NFC) to ensure consistent characters for quotes and math symbols.
- **Standardize headings:** Map common variants to canonical forms:
  - **Examples:**
    - **Abstract:** “Summary”, “Overview”
    - **Introduction:** “Background”, “Motivation”
    - **Methods:** “Methodology”, “Approach”
    - **Results:** “Findings”, “Experiments”
    - **Discussion:** “Analysis”, “Interpretation”
    - **Conclusion:** “Conclusions”, “Future Work”
- **Segment detection:** Identify sections by headings and delimiter patterns (e.g., line breaks, capitalization, numbering).

#### Required section detection
- **Collect requested sections:** Use the user’s list as the authoritative set.
- **Match to canonical map:** Align requested names with detected headings using the standardized map.
- **Missing logic:**
  - **Flag:** If a requested section isn’t found in the text, add it to “Missing sections”.
  - **Fallback:** If missing, do not fabricate content; leave a placeholder and proceed to other sections.
- **Empty detection:**
  - **Flag:** If a detected section has < 1 non-whitespace character, mark as empty.

#### Outputs
- **Normalized text:** Cleaned and segmentable paper text.
- **Section index:** Ordered list of detected sections with start/end spans.
- **Missing/empty report:** Lists for downstream guardrails.

