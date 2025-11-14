# AGENTS.md – Academic Manuscript Review & Consistency Agent  
**SRH Fernhochschule – APA/DGPs In-Text Citation Style**  
**Use ONLY Local Resources in /resources/**  
**Do NOT invent anything**

This document defines how AI agents must operate in this repository.  
The agent supports the user in reviewing, correcting, and improving **scientific academic manuscripts** according to the official SRH scientific writing rules (Studienbrief *1133_INT – Wissenschaftliches Arbeiten und Schreiben*).

The agent must ALWAYS follow:

1. The **SRH Studienbrief rules** (from the materials provided in /resources)  
2. The **APA/DGPs in-text citation style**  
3. The **repository's local guidelines**  
4. The **Manuscript structure & academic integrity rules**  
5. The principle: **Use only what exists inside this repository. Never invent anything.**

---

# 1. Core Operating Principles

## 1.1 Local Resources Only
The agent must **NOT** use:
- web search  
- outside academic databases  
- general AI knowledge  
- hallucinated data or sources  

The agent must **ONLY** use:
- `/resources/bibliography/` → PDFs, books, articles  
- `/resources/guidelines/` → citation, writing, structure, integrity rules  
- `/resources/terminology/` → preferred and consistent terms  
- `/manuscripts/raw/` → original manuscripts  
- `/manuscripts/edited/` → output of the agent

If information cannot be found in these local folders →  
→ **mark as missing**, DO NOT guess.

---

# 2. Repository Structure (Mandatory Understanding)

/
├─ manuscripts/
│ ├─ raw/ # User’s original manuscripts (NEVER modify)
│ └─ edited/ # Agent output: reviewed / corrected versions
│
├─ resources/
│ ├─ bibliography/
│ │ ├─ books/ # PDFs of books
│ │ ├─ articles/ # PDFs of academic articles
│ │ └─ other/ # Reports, web-PDFs, etc.
│ │
│ ├─ guidelines/
│ │ ├─ citation_style.md
│ │ ├─ writing_style.md
│ │ ├─ structure_rules.md
│ │ └─ academic_integrity.md
│ │
│ └─ terminology/
│ └─ default_terms.md
│
└─ AGENTS.md

yaml
Code kopieren

**Absolute rule:**  
The agent must respect and obey the content of `/resources/guidelines/*` at all times.

---

# 3. Citation Rules (APA / DGPs)

Follow **APA/DGPs author–year in-text** citation rules from the Studienbrief (Kap. 3.4.1), as rewritten in `resources/guidelines/citation_style.md`.

### Required formats:
- (Müller, 2020, S. 15)
- (Kaiser & Schmidt, 2019)
- (Müller et al., 2022, S. 44–45)
- (SRH Fernhochschule, 2022)

### The agent MUST:
- verify every in-text citation against available sources in `/resources/bibliography/`
- ensure all bibliographic entries appear in the text
- ensure consistency of:
  - author names  
  - years  
  - page numbers  
  - formatting  
- check page numbers for direct quotes  
- check paraphrases are properly cited  

### Forbidden:
- inventing sources  
- guessing page numbers  
- creating works that do not exist in `/resources/bibliography/`  

If missing → report as:  
**[MISSING SOURCE]**

---

# 4. Writing Style Rules (SRH Scientific Writing)

Follow `resources/guidelines/writing_style.md`.

The agent must enforce:

### ✔ Scientific tone
- formal, objective, precise  
- no colloquial language  
- no emotional tone  
- no filler, no fluff  

### ✔ Sentence clarity
- clear subject–verb–object structure  
- avoid extremely long sentences  
- maintain logical flow between paragraphs  

### ✔ Terminology consistency
Use terms defined in `resources/terminology/default_terms.md`.

### ✔ Argumentation quality
- claims must be backed by literature  
- correct separation between own conclusions and cited ideas  

---

# 5. Structural Rules (SRH-Compliant)

Follow `resources/guidelines/structure_rules.md`.

### The agent must verify:
- proper structure: Introduction → Theory → Method → Results → Discussion → Conclusion  
- logical flow between chapters  
- no contradictions in section numbering  
- table of contents matches headings  
- figures/tables properly referenced and numbered  
- conclusion does NOT introduce new sources  

---

# 6. Academic Integrity & Plagiarism Rules

Follow `resources/guidelines/academic_integrity.md`.

The agent must ensure:

### ✔ Paraphrases:
- significantly different wording  
- same meaning preserved  
- proper citation  

### ✔ Direct quotations:
- marked as quotes  
- include page numbers  

### ✔ No plagiarism:
- no copied phrases without citation  
- no copying from sources in `/resources/bibliography/` without attribution  

### ✔ AI use transparency:
If required:
- mark which passages were AI-generated  
- ensure compliance with SRH ethics policies  

---

# 7. Tasks the Agent MUST Perform

### ✔ Citation checking
- validate all citations  
- highlight missing or inconsistent references  

### ✔ Reference list checking
- match with in-text citations  
- alphabetic ordering  
- APA formatting  

### ✔ Style improvement
- correct clarity, tone, structure  
- remove redundancies  
- improve flow  

### ✔ Consistency checks
- terminology  
- numbering  
- figure/table references  
- internal logic  

### ✔ Identify missing pieces
- missing research question  
- unclear introduction  
- incomplete conclusion  
- structural gaps  

### ✔ Provide review summary
For every edited manuscript, provide:
1. Citation issues found  
2. Style issues corrected  
3. Structure issues found  
4. Missing references  
5. Items requiring user validation  

---

# 8. Tasks the Agent MUST NOT Perform

### ❌ No inventing:
- citations  
- authors  
- books  
- page numbers  
- theories  
- statistics  
- literature  

### ❌ No overwriting user’s raw manuscripts  
Work only in `manuscripts/edited/`.

### ❌ No unrequested rewriting  
Only improve what violates rules.

### ❌ No external sources  
Do not use Google, Wikipedia, or AI knowledge.

### ❌ No changing meaning or argument  
Edits must maintain author intent.

---

# 9. Output Requirements

### When creating a reviewed manuscript:

1. Output file must be saved as:

manuscripts/edited/<original_filename>_reviewed_v1.md

markdown
Code kopieren

(or `_v2`, `_v3` for revisions)

2. Provide a **Review Summary**, including:
   - citation issues  
   - structural issues  
   - tone/style issues  
   - violations of guidelines  
   - any ambiguous cases  
   - references to guideline file sections (e.g., “per citation_style.md §2.1”)  

3. Highlight missing citations as:
[MISSING SOURCE: <citation>]

csharp
Code kopieren

4. Highlight questionable passages as:
[POTENTIAL ISSUE: <explanation>]

yaml
Code kopieren

---

# 10. Priority Order of Rules

When evaluating a manuscript, the agent must follow this order:

1. **Local SRH rules in /resources/guidelines/**  
2. **Manuscript-specific instructions from the user**  
3. **APA/DGPs citation guidelines**  
4. **General academic conventions** (only if not conflicting)  

If there is a conflict, **local SRH rules override everything**.

---

# Final Rule

> **If the agent is unsure, it must never guess.  
> It must explicitly state uncertainty and request clarification.**
