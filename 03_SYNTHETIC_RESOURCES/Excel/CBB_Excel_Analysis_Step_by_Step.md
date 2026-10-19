# Excel KPI analysis — detailed learner reference for L23 and L24

**Use only the synthetic file** `CBB_Onboarding_Applications_480.xlsx`; this guide explains a reproducible Excel calculation method. Actual Copilot-generated formulas may differ, but their results should agree with the KPI definition.

## Important distinction

A branch can have the **most late applications by count** yet not have the **highest late percentage**. Late rate requires a clear numerator and denominator. In this exercise, count only unique, valid, completed applications.

## Create the analysis safely

1. In Excel, open the supplied `CBB_Onboarding_Applications_480.xlsx` and select **File > Save a Copy** (or the equivalent in your Excel version). Name it `L24_Working_Analysis.xlsx`.
2. Open the **Applications** sheet. The source headers are on row 4 and the records occupy rows 5–484. Keep the original columns A–O unchanged in your raw copy.
3. If Copilot proposes a different method, ask it to explain the exclusion logic and business-day counting. Compare its method with the controlled manual approach below.
4. In the **working copy**, add calculation columns **P** to **S**. Insert these headers in row 4: `Repeated_ID`, `Eligibility`, `Business_Days`, `Late_Flag`.
5. Enter these formulas in row 5 and fill down to row 484 (you can ask Copilot to help create them):

   **P5** — mark duplicate occurrences beyond the first row:
   ```excel
   =COUNTIF($A$5:A5,A5)>1
   ```

   **Q5** — classify eligible and excluded cases:
   ```excel
   =IF(P5,"DUPLICATE",IF(I5<>"Completed","OPEN",IF(OR(G5="",H5=""),"MISSING_DATE",IF(H5<G5,"INVALID_DATE","VALID"))))
   ```

   **R5** — calculate Mon–Fri duration from complete documentation (same-day completion = 0):
   ```excel
   =IF(Q5="VALID",NETWORKDAYS(G5,H5)-1,"")
   ```

   **S5** — calculate late flag (1=late, 0=on time):
   ```excel
   =IF(Q5="VALID",IF(R5>J5,1,0),"")
   ```

6. Filter **Q = VALID** to inspect eligible rows; confirm that dates make sense and that `Business_Days` is an integer 0 or greater.
7. Using PivotTables, formulas, or a Copilot-created summary, calculate by branch: **valid count** (Q = VALID), **late count** (sum of S among valid records), and **late % = late count / valid count**. The four branch names are Downtown, Marina, Creekside and Airport.
8. Create a **late percentage** column chart. Label its axis as percentage, add numerator/denominator to your notes, and log exclusion counts.
9. Check one sample row with a calendar: a case with complete documentation on Monday and completion on Thursday has duration 3 business days. For this synthetic exercise, public holidays are **not** modelled.
10. Save a one-paragraph interpretation that clearly differentiates absolute late-case counts from late rate. **Do not use the raw count 480 as the late-rate denominator.**

> **Excel note:** Functions may use semicolon separators instead of commas in some locales. Formula spelling and UI placement may differ; verify results and ask your instructor for the supported method if the formula engine behaves differently. No actual banking SLAs are represented here.

## Reflection checks

- Did you preserve the raw source as a separate copy?
- Did you document every exclusion class, not just drop rows quietly?
- Does the chart title and axis show percentage rather than count?
- Does the narrative follow the calculation rather than the manager's initial claim?
