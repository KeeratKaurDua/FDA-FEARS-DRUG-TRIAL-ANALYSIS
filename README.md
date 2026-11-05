# Drug Safety Signal Detection using FDA FAERS (Power BI)

Interactive Power BI dashboard analysing adverse event reports from the
FDA Adverse Event Reporting System (FAERS), Q2 2026.

## Objectives
1. Identify drugs with disproportionately high adverse event reporting volume.
2. Analyze serious outcomes (hospitalization, disability, death) by drug, age group and gender.
3. Track whether reporting for top drugs is rising or falling weekly (Apr-Jun 2026).
4. Compare consumer vs healthcare-professional reports, including data completeness.
5. Identify indications most frequently associated with adverse event reports.

## Dashboard
Page 1 - Overview
[Page 2 - Serious Outcomes
Page 3 - Trends, Source and Indications

## Data
- Source: FDA FAERS quarterly ASCII files (DEMO, DRUG, INDI, OUTC; REAC, THER and RPSR reviewed but not loaded).
- Link: https://www.fda.gov/drugs/fda-adverse-event-monitoring-system-aems/fda-adverse-event-monitoring-system-aems-latest-quarterly-data-files
- Raw files are not included because of size. Download Q2 2026 from the link above.
- Sample: first 500 cases of the quarter, for performance.

## Method
- Power Query (M): cleaning, deduplication (latest case version, one primary suspect drug per case), age conversion to years, age groups, reporter type mapping, outcome pivot.
- Star schema: Final_Case_Table (fact), Dim_Drug, Dim_Indication.
- 11 DAX measures: Total Reports, Serious Reports, Serious %, Deaths, Hospitalizations, Disabilities, Avg Reports per Drug, Reporting Index, HCP %, Missing Age %, Missing Indication %.

## Key findings
- 42% of reports involved a serious outcome.
- Healthcare professional reports were the most complete (12% missing age); lawyer reports had 64% missing age.
- Around half of the reports had an unknown reporter type.

## Limitations
- The 500 cases are the first records in the file, not a random sample.
- FAERS is voluntary reporting, so counts show reporting volume, not true incidence or drug danger.

## Tools
Power BI Desktop, Power Query (M), DAX
