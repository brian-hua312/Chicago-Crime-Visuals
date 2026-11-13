# Exporting Tableau visuals for GitHub

This checklist covers the 3 dashboards and 8 worksheets in `Chicago_Crime_Analytics_Dashboard_Label_Fixes.twbx`. The images do not exist in this repository yet.

## Export procedure

1. Open the packaged workbook in Tableau Desktop and save a separate copy for any temporary export-layout changes.
2. Open one dashboard or worksheet tab.
3. Select **Worksheet > Export > Image**, include the view title and relevant legends, and save as **PNG**. Tableau's export dialog is described in the [official instructions](https://help.tableau.com/current/pro/desktop/en-us/save_export_image.htm).
4. Inspect the actual exported PNG at full size before accepting it. Do not assume the export contains content hidden behind scrollbars.
5. If a worksheet contains scrollbars, try **Fit > Entire View**. If this makes marks or text too small, enlarge the sheet or export a readable additional detail image rather than squeezing the entire chart.
6. If a dashboard contains scrollbars, temporarily increase its size from the **Dashboard** pane, or export its affected worksheets individually. Keep the three dashboards as overview images and use the individual worksheets to show detailed content.
7. Verify that the exported image shows the title, legends, axis labels, complete date span, and all intended categories. Avoid cut-off marks, tiny labels, and hover tooltip boxes.
8. Upload the 11 PNG files to the project conversation for review before committing them to GitHub.

## Dashboard images

| Tableau tab | Export path |
| --- | --- |
| 01 \| Crime Overview | `images/dashboard-1-crime-overview.png` |
| 02 \| Geographic Patterns | `images/dashboard-2-geographic-patterns.png` |
| 03 \| District-Level Patterns | `images/dashboard-3-district-patterns.png` |

## Individual worksheet images

| Tableau worksheet tab | Export path |
| --- | --- |
| Chicago Reported Crime Incidents by Category (2012–2016) | `images/worksheets/01-crime-categories.png` |
| Monthly Reported Crime Incidents in Chicago (2012–2016) | `images/worksheets/02-monthly-trends.png` |
| Chicago Crime by Location: Top 15 + Other (2012–2016) | `images/worksheets/03-location-types.png` |
| Reported Crime Incidents by Police District (2012–2016) | `images/worksheets/04-police-districts.png` |
| Chicago Crime Incident Locations (2012–2016) | `images/worksheets/05-geographic-locations.png` |
| Crime Distribution in Chicago Police District 11 (2012–2016) | `images/worksheets/06-district-11-distribution.png` |
| Weekly Reported Crime Trends: Districts 8 and 11 (2012–2016) | `images/worksheets/07-weekly-trends.png` |
| Arrest Outcomes for Reported Chicago Crime Incidents (2012–2016) | `images/worksheets/08-arrest-outcomes.png` |

Tableau worksheet names in the workbook may use an em dash instead of a colon in a couple of titles. Match by content, not exact punctuation.

## Special visual checks

- **Dashboard 02, location treemap:** The combined dashboard has crowded labels. Keep the overview image, but prioritize a clear full-size export of the dedicated location-type worksheet. If the worksheet is still too crowded, use a legible supplementary image and note the limitation in the README.
- **Dashboard 01, arrest pie:** Check that category and percentage labels are legible at the exported size.
- **Year and district filters:** Verify the export displays the intended 2012–2016 date range and the correct district-specific scope. Avoid comparing a District 11 view with citywide totals without a scope note.
- **Scrolling:** If a single PNG cannot show the full worksheet legibly, export a full worksheet image if possible, otherwise prepare separate numbered detail images. Never stitch mismatched scroll positions and imply they are one Tableau output.

## README plan

The README will show the three dashboards inline. It will then link to larger individual worksheet images with a short sentence explaining what each chart displays. Numerical conclusions will be added only after verification.

**Do not add image links to the public README until the corresponding PNG files are present.**
