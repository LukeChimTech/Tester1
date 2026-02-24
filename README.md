# Engineering Documentation Version Control Guide

This repository standardizes how engineering documentation is stored, reviewed, and version‑controlled using GitHub.  
Only the following file types are used: **PDF**, **MS Word**, **Excel**, **SVG**.

---

## 1. Purpose

GitHub is used to:
- Track revisions  
- Maintain a structured audit trail  
- Support reviews and approvals through Pull Requests  
- Store finalized versions of engineering documentation  

Since PDFs, Word, Excel, and SVG files are binary (except SVG), diffs are limited.  
Git is therefore used primarily for **version tracking**, **reviews**, and **controlled storage**, not content‑level diffing.

---

## 2. Document Types in This Repository

### Design, Philosophy & Basis Documentation
- Battery Limits  
- Control Philosophy  
- Design Basis – Process  
- Design Basis – Mechanical  
- Design Basis – EC&I  
- Process Description  
- Process Design Criteria  
- Mass Balance  

### Operations & Maintenance
- Operating Manual  
- Maintenance Manual  
- Operational Functionality Sign‑off  
- Operational Functionality Punch List  

### Equipment & Fabrication
- General Equipment Sign‑off Sheet  
- General Equipment Punch List  
- Fabrication Databook  

### FAT Documentation
- FAT Protocol  
- FAT Procedure  
- FAT Sign‑off Summary  

### Process Flow & Functional Documents
- Functional Diagram  
- Network Functional Diagram  
- PFD – Ultrafiltration  
- PFD – Nanofiltration  
- PFD – CIP  

### Layouts
- Layout – Container Battery Limits  
- Layout – MCC Cabinet GA  
- Layout – Container 1 Modification  
- Layout – Container 2 Modification  

### Lists & Registers
- Actuated Valve List  
- Manual Valve List  
- Interlock List  
- Electrical & Control List  
- Equipment List  
- Instrument List  
- Line Allocation List  
- Load List – Plant  
- Load List – UPS  
- Cable Tray List  
- Range, Alarm & Trip List  
- DCS–PLC Communication List  
- Signal (IO) List  
- Sampling List  
- Tools & Spares List  

### Source Engineering Drawings
- P&ID  
- Single Line Diagrams  

### Scheduling
- Project Execution Schedule  

---

## 3. File Format Rules

| Category | Preferred Format | Notes |
|---------|------------------|-------|
| Narrative documents | PDF, Word | PDFs recommended for final issue |
| Lists & registers | Excel | Export CSV optional for diff clarity (if desired) |
| Diagrams & layouts | PDF, SVG | SVG preferred if exported cleanly |
| Schedules | PDF, Excel | PDF recommended for issued versions |

---

## 4. Repository Folder Structure

/docs/design-basis/
/docs/philosophy/
/docs/process/
/docs/operations/
/docs/equipment/
/docs/fabrication/
/docs/fat/
/docs/layouts/
/docs/pfds/
/docs/lists/
/docs/drawings/
/docs/schedules/

Each folder contains the relevant documents as PDF/Word/Excel/SVG.

---

## 5. Version Control Method

- All updates occur in **feature branches**  
- All merges require a **Pull Request**  
- Reviewers verify document correctness and naming  
- PDFs should be regenerated for revised versions  
- Documents must include revision markers (Rev0, Rev1, etc.) in the filename

**Example file naming:**  

DesignBasis_Process_Rev1.pdf
PFD_Ultrafiltration_Rev2.svg
ActuatedValveList_Rev3.xlsx
FAT_Protocol_Rev0.docx

---

## 6. Git LFS Requirements

Because PDFs, Word, and Excel files are binary, they are tracked via **Git LFS**.

Basic setup (already configured in this repo):

git lfs install
git lfs track ".pdf" ".docx" ".xlsx" ".svg"

---

## 7. Workflow Summary

1. Create a branch for your change  
2. Add/replace updated documents  
3. Commit with clear message:  
   - `PFD UF: updated feed pressure (Rev2)`  
4. Open a Pull Request  
5. Attach comments or change notes  
6. Reviewer approves → merge to `main`

---

## 8. Responsibilities

- **Document owners** maintain source files and revisions  
- **Reviewers** verify technical accuracy  
- **Repository maintainers** enforce structure & naming  

---

## 9. Final Notes

GitHub is used here as a **controlled document repository with structured review**, not for text‑based diffing. All approved files in `main` represent the latest valid project documentation.
