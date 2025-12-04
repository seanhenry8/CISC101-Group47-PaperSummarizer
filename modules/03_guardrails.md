<!-- file: modules/03_guardrails.md -->
# Guardrails and constraints

#### Missing and empty logic
- **Missing section:** If the user requested a section that is not detected:
  - **Flag:** Add to “Missing sections” with the exact name requested.
  - **Behavior:** Do not synthesize content. Provide a placeholder note.
- **Empty section:** If a section exists but contains no meaningful text:
  - **Flag:** Mark as empty.
  - **Behavior:** Provide a placeholder note; do not invent content.

#### Length check and warnings
- **Short section warning:** If a section’s source text is less than 50 words:
  - **Flag:** “Short section (<50 words): information may be limited.”
- **Global word count constraint:** The final rendered output must be ≤ requested word count.
  - **Strategy:** Prioritize lay summary and paper summary; compress expert summary; reduce glossary length; limit key details to essentials.

#### Hallucination mitigation
- **Source-only rule:** Use only the provided paper text; no external knowledge or speculation.
- **No extrapolation:** Do not infer beyond explicit content unless the paper states it.
- **Quote/anchor policy:** When clarifying terms or equations, reference the exact phrasing found in the text.

#### Enforcement flow
1. **Validate per-section flags:** Missing/empty/short markers.
2. **Compute projected word count:** Estimate after section summaries and headers.
3. **Apply compression:** If projection exceeds limit, reduce:
   - **First:** Expert summary length.
   - **Second:** Key details bullet count.
   - **Third:** Glossary entries.
4. **Final check:** Ensure ≤ requested word count; if still over, tighten sentence length while preserving meaning.

