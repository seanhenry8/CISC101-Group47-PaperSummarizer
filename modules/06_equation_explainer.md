<!-- file: modules/06_equation_explainer.md -->
# Equation and variable explainer (Student Module B)

#### Goal
Find mathematical formulas or variable definitions and explain them in plain English a child can understand.

#### Detection logic
- **Equations:** Identify LaTeX-like patterns ($...$, 

\[...\]

, equations with =, summations, matrices).
- **Variables and symbols:** Detect definitions (“where x is…”, “let Q be…”, “denote by …”).
- **Context windows:** Capture surrounding sentences to understand purpose (losses, attention, optimization).

#### Explanation steps
1. **Extract formula:** Copy the exact equation text from the paper.
2. **List parts:** Identify variables, constants, and operations.
3. **Plain-English meaning:** Explain what the equation tries to do using simple language.
4. **Analogy:** Use friendly examples (“This is like sharing candies fairly among friends.”).
5. **Role in paper:** State where and why the equation is used (e.g., training, scoring, prediction).

#### Output format
- **Equation:** The original formula.
- **Pieces:**  
  - **Variables:** Names and what they stand for (from the text only).  
  - **Operations:** What actions the equation performs (add, average, compare).  
- **Simple explanation:** 2–4 sentences a child could follow.
- **Analogy:** 1 friendly comparison.
- **Location:** Section where found (Methods, Results, Appendix).

#### Constraints
- **Source-only:** Do not invent definitions; use only what’s given.
- **Child-friendly:** Short sentences, everyday words, clear analogies.
- **Consistency:** If the same symbol appears in multiple places, keep definitions consistent with the paper’s first introduction.

