# Chicago Crime Analytics (2012–2016)

**Exploratory analysis and data visualization using Tableau**

## Overview

I used Tableau to explore reported crime incidents in Chicago from 2012 through 2016. I compared incident counts by crime category, month, location type, police district, and arrest status. I organized the results into three dashboards and kept eight individual worksheets so each chart can also be viewed in detail.

The dashboard images are available below and you can select a Tableau Public link to explore the interactive version.

## Dashboards

### 1. Citywide Crime Overview

This dashboard brings together reported incidents by category and year, monthly trends, and arrest status.

![Citywide Crime Overview](images/dashboard-1-crime-overview.png)

[Explore Citywide Crime Overview on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_Dashboard_Label_Fixes/01CrimeOverview)

### 2. Locations and Police Districts

This dashboard combines a geographic density map with police district totals and reported location types. The charts show incident counts, not population-adjusted crime rates.

![Locations and Police Districts](images/dashboard-2-geographic-patterns.png)

[Explore Locations and Police Districts on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/02GeographicPatterns)

**Viewing note:** Smaller location type labels are crowded in the treemap, and the district chart may scroll. Use the dedicated location type and police-district worksheets below to see the larger views. The map excludes records without usable coordinates.

### 3. District-Level Patterns

This dashboard shows the distribution of reported crime categories within District 11 and weekly incident trends for Districts 8 and 11. These are separate filtered views.

![District-Level Patterns](images/dashboard-3-district-level-patterns.png)

[Explore District-Level Patterns on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/03District-LevelPatterns)

## Individual Worksheets

I also kept the eight worksheets as standalone views, making it easier to read labels and examine specific comparisons.

### 1. Crime categories by year

Comparison of reported incident counts across crime categories from 2012 to 2016.

![Crime categories by year](images/worksheets/01-crime-categories.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ChicagoReportedCrimeIncidentsbyCategory20122016)

### 2. Monthly incident trends

Monthly changes in reported incident volume over the analysis period.

![Monthly incident trends](images/worksheets/02-monthly-trends.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/MonthlyReportedCrimeIncidentsinChicago20122016)

### 3. Location types: Top 15 + Other

Counts by reported location description, including a grouped Other Locations category.

![Location types: Top 15 + Other](images/worksheets/03-location-types.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ChicagoCrimebyLocationTop15Other20122016)

### 4. Police district comparisons

Reported incident counts by police district, ranked from highest to lowest.

![Police district comparisons](images/worksheets/04-police-districts.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ReportedCrimeIncidentsbyPoliceDistrict20122016)

### 5. Geographic incident density

Density map of incidents with recorded geographic coordinates.

![Geographic incident density](images/worksheets/05-geographic-locations.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ChicagoCrimeIncidentLocations20122016)

### 6. Crime distribution in District 11

Distribution of selected crime categories among District 11 incidents.

![Crime distribution in District 11](images/worksheets/06-district-11-distribution.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/CrimeDistributioninChicagoPoliceDistrict1120122016)

### 7. Weekly trends in Districts 8 and 11

Comparison of reported weekly incident counts in two police districts.

![Weekly trends in Districts 8 and 11](images/worksheets/07-weekly-trends.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/WeeklyReportedCrimeTrendsDistricts8and1120122016)

### 8. Arrest outcomes

Share of incidents with an arrest recorded versus no arrest recorded.

![Arrest outcomes](images/worksheets/08-arrest-outcomes.png)

[Explore this worksheet on Tableau Public](https://public.tableau.com/app/profile/brian.hua1739/viz/Chicago_Crime_Analytics_With_Dashboards/ArrestOutcomesforReportedChicagoCrimeIncidents20122016)

## Data and Scope

- **Dataset:** [City of Chicago Data Portal, Crimes - 2001 to Present](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2)
- **Displayed period:** 2012–2016
- **Primary measure:** Counts of reported crime incidents
- **Tools:** Tableau, Tableau Public

The workbook's source connection was originally named for a 2012–2017 dataset. The updated views are filtered to 2012–2016. In a separate Tableau Public validation worksheet, I confirmed that the source dates run from January 1, 2012, to January 18, 2017. The data therefore include only part of 2017. The latest date in 2016 is December 31, 2016, and 63 records have missing dates. These checks support the selected 2012–2016 window, although they do not prove that every incident was reported.

## Tableau Workbook

The interactive dashboards and worksheets are available through the links above. To open the complete project in Tableau, download the [packaged Tableau workbook (`Chicago_Crime_Analytics_Final.twbx`)](Chicago_Crime_Analytics_Final.twbx). It contains the final project worksheets and dashboards, along with the embedded data extract.

The full workbook is stored using Git LFS.

## Findings

I reproduced the figures below in separate Tableau Public validation worksheets using the same 2012–2016 year filter as the published views. These are findings from the workbook's embedded data, not an external reconciliation against the City of Chicago's live dataset.

**Reported theft incidents decreased 18.9% from 2012 to 2016.** Theft fell from 75,450 to 61,163 incidents, a decrease of 14,287. Theft was the largest reported crime category in both years. [Crime categories by year](images/worksheets/01-crime-categories.png)

**Recorded narcotics incidents decreased 65.0%.** Narcotics fell from 35,486 in 2012 to 12,413 in 2016, a decrease of 23,073. The change is substantial, but the data do not establish how much it reflects crime patterns versus enforcement or reporting practices. [Crime categories by year](images/worksheets/01-crime-categories.png)

**District 11 had the most reported incidents among the 22 districts compared.** District 11 had 102,096 incidents, followed by District 8 with 95,575 and District 6 with 86,169. I also checked district codes outside the 22-district comparison: 26 records used code 31, one used code 13, and one had no district value. Those 28 records are excluded from the district comparison, not from the underlying dataset. The totals are not adjusted for population. [Police district comparison](images/worksheets/04-police-districts.png)

**An arrest was recorded for 25.99% of incidents.** The arrest-status analysis includes 375,564 incidents with an arrest recorded and 1,069,730 without one, out of 1,445,294 incidents in total. These counts were reproduced in a separate worksheet. An arrest record is not the same as a conviction. [Arrest outcomes](images/worksheets/08-arrest-outcomes.png)

**Street was the most frequent reported location description.** There were 327,771 incidents marked STREET, followed by 231,509 marked RESIDENCE. I checked the top 15 raw location descriptions against their ranking and reproduced the calculated **Other Locations** grouping of 207,466 incidents. The raw `OTHER` description is a separate category from `Other Locations`. [Location types](images/worksheets/03-location-types.png)

## Data Validation and Limitations

I validated the main counts and calculations in separate Tableau Public worksheets:

- **Dates:** The extract spans January 1, 2012, through January 18, 2017. I filtered the analysis to 2012–2016 to avoid the partial 2017 period. The last incident date in 2016 is December 31, and 63 records have missing dates. Date-boundary checks do not establish complete incident reporting throughout every year.
- **Monthly trend:** The 2012–2016 total is 1,445,294 incidents across 60 months, giving a validated mean of **24,088.23 incidents per month**. The previously exported monthly worksheet image shows a reference line labeled approximately 24,200. That reference line still needs to be reviewed and corrected in the published view if it is intended to represent the same 60-month mean.
- **Geographic coverage:** 25,756 incidents (approximately **1.78%** of the 2012–2016 total) have missing longitude values and are excluded from the geographic map. A broader test for missing or out-of-range coordinates found no additional records. The remaining coordinates have not been independently geocoded.
- **Location and district scope:** The top 15 location grouping is a fixed list that was checked against the current extract's ranking. The district comparison covers 22 selected operational districts rather than every historic or administrative code in the source.
- **Interpretation:** The source contains *reported* incidents. Differences across districts can reflect population, activity levels, reporting practices, and enforcement. Counts and visual patterns cannot establish individual risk or the causes of change.

The full calculations, filter checks, and remaining caveats are documented in the [verification audit](docs/VERIFICATION_AUDIT.md).

## Project Files

- [Dashboard screenshots](images/)
- [Individual worksheet screenshots](images/worksheets/)

SQL scripts and independent query-performance benchmarks are not included in this version of the project.
