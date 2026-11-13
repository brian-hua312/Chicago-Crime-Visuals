# Workbook Verification Audit

**Audit date:** November 13, 2026  
**Workbook inspected:** `Chicago_Crime_Analytics_Dashboard_Label_Fixes.twbx`

This audit inspects the Tableau workbook's XML definitions and independently recalculates percentages from values shown in the published worksheets. **It does not independently query the embedded `.hyper` extract.** The workbook ZIP integrity check passed and the embedded extract is present.

## Confirmed workbook settings

- The workbook contains eight worksheets and three dashboards.
- Every worksheet filters Year(Date) to **2012–2016**, inclusive.
- There are no additional Tableau data-source-level filters defined in the workbook XML.
- The District 11 category visualization filters to **District 11**.
- The weekly trend visualization filters to **Districts 8 and 11**.
- The police district comparison explicitly includes 22 district values (1–12, 14–20, 22, 24, 25), rather than automatically including all possible district values.
- The geographic map explicitly excludes null longitude values. Additional coordinate completeness and map validity checks have not been performed.
- Arrest labels use the calculation: `IF [Arrest] THEN "Arrest Recorded" ELSE "No Arrest Recorded" END`.
- The “Top 15 + Other” location chart uses a **hardcoded list of 15 location descriptions**. It is not a dynamically recomputed Top 15 ranking. All other location descriptions are grouped as “Other Locations.”

## Arithmetic checks based on published Tableau counts

| Comparison | Published values | Independently calculated | Status |
| --- | --- | --- | --- |
| Theft, 2012 to 2016 | 75,450 to 61,163 | Decrease of 14,287 (18.94%) | Arithmetic matches |
| Narcotics, 2012 to 2016 | 35,486 to 12,413 | Decrease of 23,073 (65.02%) | Arithmetic matches |
| Battery, 2012 to 2016 | 59,126 to 50,239 | Decrease of 8,887 (15.03%) | Arithmetic matches |
| Arrest recorded | 375,564 | 25.9853% of displayed total | Matches displayed 25.99% |
| No arrest recorded | 1,069,730 | 74.0147% of displayed total | Matches displayed 74.01% |
| Arrest outcome total | 375,564 + 1,069,730 | 1,445,294 incidents | Arithmetic matches |

The arithmetic check establishes internal consistency of **displayed counts**. It does not confirm that the extract's source records independently produce those values.

## Checks still required against the embedded extract

1. Independently query minimum/maximum Date, records with missing Date, and counts by Year(Date). Confirm the completeness of 2012–2016 before making full-year comparisons.
2. Recalculate counts by Primary Type and year from incident-level records.
3. Reconcile citywide incident count by month and confirm the monthly chart's reference line.
4. Recalculate totals for all 22 listed districts and check for incidents with null or other district codes.
5. Verify that the 15 fixed location descriptions truly represent the largest categories in the filtered extract. Verify the count of “Other Locations.”
6. Recalculate arrest counts and percentages directly from the extract, including treatment of null Arrest values.
7. Check both latitude and longitude for missing or invalid values, and document how many geographic incidents are omitted.
8. Verify percentage-of-total partitioning for the District 11 crime-distribution chart.

## Reporting decision

Keep README findings labeled **preliminary** until the independent extract-level reconciliations above are complete. Do not claim that the 2012–2016 source data are complete or that changes in recorded incident counts demonstrate causal effects.
