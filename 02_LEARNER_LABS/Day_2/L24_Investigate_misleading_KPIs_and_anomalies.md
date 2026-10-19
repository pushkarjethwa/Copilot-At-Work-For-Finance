---
lab:
  title: 'Investigate misleading KPIs and anomalies'
  module: 'M09'
  duration: '55 minutes'
  level: 'Challenge'
  tool: 'Excel with Copilot'
---
# L24 — Investigate misleading KPIs and anomalies

**Goal:** Evaluate a manager’s branch-rate claim using independent Excel formulas.  
**Time:** 55 minutes (14 + 28 + 13).    
**Scenario:** A draft management report claims Downtown has the worst late-processing rate. All cases, customers and data are synthetic.

Check the shared Lab Basics page before handling audited exclusions, five case checks and a corrected branch comparison; use the Prompt Recipe if the response lacks evidence. Save only to your individual training folder.

## Sources and tools — Investigate misleading KPIs and anomalies

- **Application:** Excel with Copilot.
- **Source:** `CBB_10_KPI_Definitions.docx`, `CBB_Excel_Analysis_Step_by_Step.md`, `CBB_Onboarding_Applications_480.xlsx`.
- **Save location:** your personal `My_Work/L24_My_Work`, not the shared source; this activity uses Excel with Copilot.

## Open Copilot for this exercise — Investigate misleading KPIs and anomalies

Open a **personal copy** of the workbook in supported Excel. Locate the **Applications** worksheet and the `CBBApplications` Excel Table (headers on row 4). Open **Copilot** from the ribbon. Keep source columns unchanged; inspect formulas manually against the KPI definition.

> **[CONFIRM IN TENANT: screenshot here]** Capture the actual Excel with Copilot entry point used in L24. App access and names remain untested.

**Calculation reference:** `03_SYNTHETIC_RESOURCES/Excel/CBB_Excel_Analysis_Step_by_Step.md` explains the formulas and denominator.

## Activity: Investigate misleading KPIs and anomalies

### Part A — Read and identify the evidence: audited exclusions, five case checks and a corrected branch comparison (14 min)

1. Open a personal copy of `CBB_Onboarding_Applications_480.xlsx`, sheet **Applications**, and confirm headers on row 4.
2. Ask Copilot to identify ID duplicates, open cases, missing dates and invalid chronology as four separate exclusion categories.
3. Apply unique-record rules and compute business-day duration from complete documentation, not received date.

> **Checkpoint:** You should now have the source materials open and a first note on audited exclusions, five case checks and a corrected branch comparison.
### Part B — Make a first draft and challenge it: audited exclusions, five case checks and a corrected branch comparison (28 min)

1. Open `CBB_Excel_Analysis_Step_by_Step.md` and follow the row-5 formulas P5:S5 on your personal copy.
2. Contrast the branch with the most late cases against the branch with the largest late percentage.
3. Test the effect of incorrectly counting open cases in the denominator, then restore the valid method.

> **Checkpoint:** You should now see audited exclusions, five case checks and a corrected branch comparison in your draft, with any uncertain statements marked.
### Part C — Verify the output and store it: audited exclusions, five case checks and a corrected branch comparison (13 min)

1. Make a chart labelled as late RATE (%) and draft three evidence-based recommendations.
2. In the Applications table, find these five IDs and check their dates: CBB-SYN-0001, CBB-SYN-0002, CBB-SYN-0006, CBB-SYN-0012, CBB-SYN-0021; do not assume they have the same status.
3. Save `L24_My_Work` with your evidence for audited exclusions, five case checks and a corrected branch comparison; reopen the file and confirm the evidence is visible.

> **Checkpoint:** Your saved work includes an evidence check; point to the Eligibility and Late_Flag calculation columns.

## Prompt practice for investigate misleading kpis and anomalies

1. **Starter:** “Find data-quality problems affecting this branch late-rate report.” Enter this with the synthetic document open; replace any names in brackets with facts from the named source.
2. **Improve:** “Group duplicate IDs, open cases, missing dates and invalid chronology.” Compare the second response with the first, retaining your own prompt edits.
3. **Check:** “Does a high late count also imply the highest late rate?” Do a manual source check before accepting the response.

## Inspect a successful investigate misleading kpis and anomalies result

A concise result makes audited exclusions, five case checks and a corrected branch comparison easy to inspect. Point to the Eligibility and Late_Flag calculation columns. This is a format example, not a substitute for doing the activity.

### Responsible AI check (included in Part C)

Numeric integrity: recalculate every rate and disclose exclusions. Use the Accuracy → Privacy → Approval → Source checklist.

## Help for this activity — Investigate misleading KPIs and anomalies

- **Hint 1:** Open `CBB_10_KPI_Definitions.docx` and identify its title, status or relevant field before prompting.
- **Hint 2:** Read the part of the source that relates to this issue: point to the Eligibility and Late_Flag calculation columns.
- **Hint 3:** If Copilot is unavailable, open `CBB_10_KPI_Definitions.docx`, write the requested comparison or draft manually, and label the submission ‘offline source-only’.

## Review the evidence for investigate misleading kpis and anomalies

- [ ] My submission addresses the source question: What is the difference between the most late cases and the highest late rate?
- [ ] I checked for a common error: using the received date instead of documentation completion.
- [ ] My saved artifact gives the reader audited exclusions, five case checks and a corrected branch comparison.

## Reflection — Investigate misleading KPIs and anomalies

What is the difference between the most late cases and the highest late rate? Write a short answer next to your saved filename. Do not send training drafts to real bank customers.
