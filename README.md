# Chicago Crime Analytics (2012–2016)

**Tableau analysis of reported crime incidents in Chicago**

## Overview

I used Tableau to explore reported crime incidents in Chicago, focusing on 2012 through 2016. I compared incident counts across crime categories, months, police districts, location types, and arrest status. I built three combined dashboards to make the results easier to explore and kept the eight individual worksheets for more detailed viewing.

**Project status:** The dashboard documentation is published. The packaged Tableau workbook and screenshots are being added, and I am reviewing the numerical findings before including them here.

## Dashboards

| Dashboard | What it covers |
| --- | --- |
| **01: Crime Overview** | Reported crime categories by year, monthly incident trends, and whether an arrest was recorded |
| **02: Geographic Patterns** | Geographic incident locations, police district comparisons, and reported location types |
| **03: District-Level Patterns** | Crime categories within District 11 and weekly incident trends for Districts 8 and 11 |

**Viewing note:** The location-type treemap on Dashboard 02 has crowded labels in smaller tiles. The dedicated worksheet **Chicago Crime by Location: Top 15 + Other (2012–2016)** provides a larger view. This is a presentation limitation, not a change in the underlying records.

## Data and scope

- **Source:** [City of Chicago Data Portal, Crimes - 2001 to Present](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2)
- **Displayed analysis period:** 2012–2016
- **Measure:** Counts of reported incident records, not population-adjusted crime rates
- **Workbook:** Tableau packaged workbook (`.twbx`) containing an embedded data extract

The underlying connection was originally named for a 2012–2017 dataset. The updated worksheets use filters for 2012–2016. I still need to check the exact date coverage and missing-date records before making detailed annual comparisons.

## Workbook contents

The eight worksheets examine:

1. Reported incidents by crime category and year
2. Monthly incident trends
3. Top location types and other locations
4. Police district comparisons
5. Geographic incident locations
6. Crime categories within District 11
7. Weekly patterns in Districts 8 and 11
8. Arrest-recorded versus no-arrest-recorded incidents

Some views have district-specific filters and should not be interpreted as citywide totals. The arrest field indicates a recorded arrest status, not a conviction.

## Open the Tableau project

**The packaged workbook is not yet uploaded to this repository.** Once `Chicago_Crime_Analytics.twbx` is added using Git LFS, download it and open it in a compatible version of Tableau Desktop or Tableau Reader. Start with the three dashboards, then use the individual worksheet tabs for larger views.

There is no Tableau Public link yet.

## Findings and limitations

I am reviewing the results before publishing specific numerical findings. I plan to verify category changes, incident trends, location groupings, and arrest-status shares against the workbook and its filters.

The data represent reported incidents rather than every crime committed. Reporting practices and differences in population or exposure can affect comparisons. Counts have not been adjusted for population, and visual patterns alone do not establish why crime changed.

See [Analysis review checklist](docs/ANALYSIS_NOTES.md) for the checks in progress.

## Tools

- Tableau for visualizations and dashboard layout
- City of Chicago open crime data

This repository does not currently include SQL scripts or independently verified SQL performance benchmarks.
