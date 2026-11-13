# Chicago Crime Analytics (2012–2016)

**Tableau analysis of reported crime incidents in Chicago**

## Overview

I used Tableau to explore reported crime incidents in Chicago, focusing on 2012 through 2016. I compared incident counts across crime categories, months, police districts, location types, and arrest status. I built three combined dashboards to make the results easier to explore and kept the eight individual worksheets for more detailed viewing.

**Project status:** The dashboard documentation is published. The packaged Tableau workbook and screenshots are being added, and I am reviewing the numerical findings before including them here.

## Dashboards

| Dashboard | What it covers |
| --- | --- |
| **01: Crime Overview** | Reported crime categories by year, monthly incident trends, and whether an arrest was recorded |
| **02: Geographic Patterns** | Geographic incident locations, police district comparisons, and reported location types. [View interactively on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/02GeographicPatterns) |
| **03: District-Level Patterns** | Crime categories within District 11 and weekly incident trends for Districts 8 and 11. [View interactively on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/03District-LevelPatterns) |

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


## Explore individual worksheets

Each worksheet is available interactively on Tableau Public. Static PNGs will be added after the image files are uploaded to this repository.

| Worksheet | Interactive view |
| --- | --- |
| 01. Reported crime categories by year | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ChicagoReportedCrimeIncidentsbyCategory20122016) |
| 02. Monthly reported incident trend | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/MonthlyReportedCrimeIncidentsinChicago20122016) |
| 03. Reported incident location types | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ChicagoCrimebyLocationTop15Other20122016) |
| 04. Reported incidents by police district | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ReportedCrimeIncidentsbyPoliceDistrict20122016) |
| 05. Geographic density of reported incidents | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ChicagoCrimeIncidentLocations20122016) |
| 06. District 11 crime distribution | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/CrimeDistributioninChicagoPoliceDistrict1120122016) |
| 07. Weekly reported incidents in Districts 8 and 11 | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/WeeklyReportedCrimeTrendsDistricts8and1120122016) |
| 08. Arrest status of reported incidents | [Open in Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ArrestOutcomesforReportedChicagoCrimeIncidents20122016) |

## Open the Tableau project

**The packaged workbook is not yet uploaded to this repository.** Once `Chicago_Crime_Analytics.twbx` is added using Git LFS, download it and open it in a compatible version of Tableau Desktop or Tableau Reader. Start with the three dashboards, then use the individual worksheet tabs for larger views.

[Explore Dashboard 02: Geographic Patterns on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/02GeographicPatterns). Dashboard screenshots will be added after the PNG files are uploaded.

## Findings and limitations

I am reviewing the results before publishing specific numerical findings. I plan to verify category changes, incident trends, location groupings, and arrest-status shares against the workbook and its filters.

The data represent reported incidents rather than every crime committed. Reporting practices and differences in population or exposure can affect comparisons. Counts have not been adjusted for population, and visual patterns alone do not establish why crime changed.

See [Analysis review checklist](docs/ANALYSIS_NOTES.md) for the checks in progress.

## Tools

- Tableau for visualizations and dashboard layout
- City of Chicago open crime data

This repository does not currently include SQL scripts or independently verified SQL performance benchmarks.
