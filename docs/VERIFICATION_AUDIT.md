# Chicago Crime Analytics: Data Validation

I used separate worksheets in Tableau Public to check the values shown in my Chicago Crime Analytics dashboards. My goal was to make sure the published charts used consistent filters, counts, and calculations before documenting the findings.

The analysis covers reported incidents dated **2012 through 2016**. Unless noted otherwise, I used the same year filter in each validation worksheet. These checks use the data extract in my Tableau workbook, not a fresh download or a separate query of the city's source dataset.

## Incident totals and date coverage

I created a worksheet that counted all records with dates in the analysis period and got **1,445,294 incidents**. I also checked the earliest and latest dates in the extract without applying a year filter.

| Check | Result |
| --- | --- |
| Incidents dated 2012–2016 | 1,445,294 |
| Earliest date in extract | January 1, 2012, 12:00 AM |
| Latest date in extract | January 18, 2017, 11:49 PM |
| Latest incident date in 2016 | December 31, 2016 |
| Records with missing dates, unfiltered extract | 63 |

I counted missing dates with this Tableau calculation:

```tableau
IF ISNULL([Date]) THEN 1 ELSE 0 END
```

I summed the flag without a date filter. The 63 records with missing dates are not part of the year-filtered results. I kept the analysis focused on 2012–2016 because the extract only includes part of January 2017. These date checks confirm the observed boundaries, but they do not prove that every incident during 2012–2016 was reported or captured.

## Crime categories by year

I built a separate table with `Primary Type` on Rows, discrete `YEAR(Date)` on Columns, and incident count as the measure. The counts below matched the published crime-category worksheet.

| Category | 2012 | 2016 | Change |
| --- | ---: | ---: | ---: |
| Theft | 75,450 | 61,163 | -14,287 (-18.94%) |
| Narcotics | 35,486 | 12,413 | -23,073 (-65.02%) |
| Battery | 59,126 | 50,239 | -8,887 (-15.03%) |

These figures describe changes in *reported* incidents. They do not explain what caused the changes.

## Monthly incident trend

I grouped the 2012–2016 incidents by month in a separate worksheet and checked the average across the **60 months**.

| Measure | Result |
| --- | ---: |
| Total incidents | 1,445,294 |
| Months | 60 |
| Average incidents per month | 24,088.23 |

The existing exported monthly chart shows a reference line labeled approximately **24,200**. I retained the published visualization and am documenting the difference here. The verified 60-month mean is 24,088.23; the chart's reference line should not be interpreted as that exact mean.

## Police district counts

I checked district totals using the 2012–2016 year filter.

| District | Reported incidents |
| --- | ---: |
| 11 | 102,096 |
| 8 | 95,575 |
| 6 | 86,169 |

The district comparison uses a specified set of **22 districts**: 1–12, 14–20, 22, 24, and 25. I checked the historical and missing codes separately:

| District value outside the comparison | Records |
| --- | ---: |
| 13 | 1 |
| 21 | 0 |
| 23 | 0 |
| 31 | 26 |
| Missing district | 1 |
| **Total** | **28** |

The 28 records listed above are excluded from the 22-district chart, but not deleted from the dataset. This check covers the listed historical and missing codes rather than a separate exhaustive reconciliation of every possible district value. District totals are counts, not population-adjusted crime rates.

## Reported location types

To check the location chart, I sorted the raw `Location Description` values by incident count. The 15 largest categories matched the fixed list used in the published `Top 15 + Other` view.

| Rank | Location description | Incidents |
| ---: | --- | ---: |
| 1 | STREET | 327,771 |
| 2 | RESIDENCE | 231,509 |
| 3 | APARTMENT | 183,403 |
| 4 | SIDEWALK | 160,186 |
| 5 | OTHER | 55,316 |
| 6 | PARKING LOT/GARAGE | 41,370 |
| 7 | ALLEY | 31,542 |
| 8 | RESIDENTIAL YARD | 30,469 |
| 9 | SMALL RETAIL STORE | 28,528 |
| 10 | SCHOOL, PUBLIC | 25,851 |
| 11 | RESTAURANT | 25,562 |
| 12 | RESIDENCE-GARAGE | 25,503 |
| 13 | RESIDENCE-PORCH | 25,339 |
| 14 | VEHICLE NON-COMMERCIAL | 24,937 |
| 15 | DEPARTMENT STORE | 20,542 |

I then used the workbook's `Location Type - Top 15 + Other` calculated field in a separate worksheet. The **Other Locations** group contained **207,466 incidents**, matching the published chart.

The original location description `OTHER` is not the same thing as the calculated `Other Locations` group. Also, the Top 15 list is fixed in the workbook. It will not automatically change if newer data have a different ranking.

## Arrest status

I reproduced the arrest counts in another Tableau worksheet with the same 2012–2016 filter.

| Recorded status | Incidents | Share |
| --- | ---: | ---: |
| Arrest Recorded | 375,564 | 25.99% |
| No Arrest Recorded | 1,069,730 | 74.01% |
| **Total** | **1,445,294** | **100%** |

The workbook labels status using:

```tableau
IF [Arrest] THEN "Arrest Recorded"
ELSE "No Arrest Recorded"
END
```

This field describes whether an arrest was recorded. It does not indicate whether a person was convicted or how a case was resolved.

## District 11 crime distribution

I filtered a validation worksheet to District 11, used the existing `Crime Type - Top 10 + Other` grouping, and calculated each category's percentage of the district total.

| Crime category | Share of District 11 incidents |
| --- | ---: |
| Narcotics | 28.00% |
| Battery | 18.71% |
| Theft | 11.18% |
| Criminal Damage | 7.82% |
| Assault | 5.91% |

These five percentages matched the published District 11 chart. I did not separately recalculate every remaining category in the grouping from raw incident records.

## Geographic coordinate coverage

For the 2012–2016 records, I compared two checks: missing longitude values, and a broader test for missing or out-of-range latitude or longitude.

```tableau
IF ISNULL([Longitude]) THEN 1 ELSE 0 END
```

The broader calculation was:

```tableau
IF ISNULL([Latitude])
   OR ISNULL([Longitude])
   OR ABS([Latitude]) > 90
   OR ABS([Longitude]) > 180
THEN 1
ELSE 0
END
```

| Coordinate check | Incidents |
| --- | ---: |
| Missing longitude | 25,756 |
| Missing or out-of-range coordinates | 25,756 |

Both checks returned the same total. The broader test did not identify additional records beyond those already missing longitude.

The geographic map excludes null longitude values. That affects **25,756 incidents, or approximately 1.78%** of the 1,445,294 incidents in the analysis. The other **1,419,538** records were not flagged by these tests. This does not guarantee that every remaining coordinate is correctly located in Chicago.

## Workbook setup and limitations

The workbook configuration review identified three dashboards, eight analytical worksheets, and year filters set to 2012–2016. The District 11 view is filtered to that district, while the weekly comparison is filtered to Districts 8 and 11. The location grouping and district selections described above are fixed in their respective worksheets.

My validation focused on reproducing the published results in Tableau Public. I did not run a separate record-level audit against the source data or independently verify the accuracy of the city's underlying incident reports. Reported incident counts can be affected by reporting practices, enforcement, and differences in activity or population across locations. I treat these charts as descriptive analysis, not evidence of causation.
