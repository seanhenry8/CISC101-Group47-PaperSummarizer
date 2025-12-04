<!-- file: modules/05_citation_extractor.md -->
# Citation and reference extractor (Student Module A)

#### Goal
Identify and list key references or citations mentioned in the text to help users see which prior work the paper builds on.

#### Detection logic
- **Inline citations:** Recognize patterns like “[1]”, “[2, 3]”, “(Smith et al., 2017)”, “Smith and Jones (2019)”.
- **Reference section:** Detect headings such as “References”, “Bibliography”, “Works Cited”.
- **Anchors:** Link inline markers to full entries when a reference section is present.

#### Extraction steps
1. **Scan for citation markers:** Collect unique inline tokens and author-year mentions.
2. **Locate reference entries:** Parse numbered or author-year lists under the reference heading.
3. **Map citations:** Match inline markers to full entries; if unmapped, record inline mention only.
4. **Rank key references:** Prioritize those cited in Abstract, Introduction, and Methods; count frequency.

#### Output format
- **Key references list:**  
  - **Citation:** Full reference text or author-year.  
  - **Frequency:** Count of mentions across sections.  
  - **Context:** Sections where cited (e.g., Abstract, Methods).  
- **Unresolved citations:**  
  - **Marker:** Inline token without a matching full entry.  
  - **Location:** Section and sentence snippet.

#### Constraints
- **Source-only:** Do not infer missing bibliographic details; report exactly what’s present.
- **Child-friendly note:** Provide a simple one-line explanation of why each key reference matters (“This paper learns from…”).

