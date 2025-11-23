# Iris-EDA-project

#Insurance Analysis Dashboard – Power BI:

Dashboard Link: https://app.powerbi.com/links/EAk75CoHKH?ctid=7044c926-8a70-488f-8a35-68c95f6772c0&pbi_source=linkShare
Problem Statement

This dashboard provides a complete overview of customer behavior, insurance claims, policy patterns, and risk indicators to help insurance companies make data-driven decisions.
It highlights customer satisfaction, claim performance, policy distribution, risk segments, premium trends, and demographic insights.
By analyzing these factors, insurers can identify claim delays, high-risk customers, policy profitability, and service improvement opportunities.

The dashboard also helps identify:

Policy categories contributing most to revenue

Claim types with higher rejection rates

Customer age groups with highest claim frequency

Trends in premium payments and claim settlement time

Overall, the insights guide insurance businesses in reducing claim delays, improving customer satisfaction, and optimizing policy offerings.

Steps Followed
Step 1:

Loaded the insurance dataset (.csv) into Power BI Desktop.

Step 2:

Opened Power Query editor → Enabled Column Quality, Column Distribution, and Column Profile under View.

Step 3:

Switched profiling to “Entire dataset” instead of default 1000 rows.

Step 4:

Identified missing values in fields such as Claim Amount, Settlement Time, etc.
Null values were ignored wherever not relevant for calculations (e.g., computing averages).

Step 5:

A theme was applied from View → Themes to maintain a clean, uniform design.

Step 6:

Created slicers for important filters:

Policy Type

Customer Type

Claim Status

Region

Age Group

These slicers allow dynamic analysis based on customer segments.

Step 7:

Designed KPI card visuals for:

Total Customers

Total Policies

Total Claim Amount

Average Settlement Time

Total Premium Collected

Step 8:

Added bar/column charts to show:

Claim Approval vs Rejection

Policy distribution by category

Customers by age group

Claim frequency by region

Step 9:

Calculated a new Age Group column using the following DAX:

Age Group =
IF(Insurance[Age] <= 25, "0-25 (25 included)",
IF(Insurance[Age] <= 50, "25-50 (50 included)",
IF(Insurance[Age] <= 75, "50-75 (75 included)",
"75-100 (100 included)")))

Step 10:

Created a measure for Total Customers

Total Customers = COUNT(Insurance[CustomerID])

Step 11:

Created a measure for Percentage of Claim Approved:

% Claims Approved =
DIVIDE(
CALCULATE(COUNT(Insurance[ClaimStatus]), Insurance[ClaimStatus] = "Approved"),
[Total Customers]
) * 100

Step 12:

Created a measure for Total Premium Collected:

Total Premium = SUM(Insurance[PremiumAmount])

Step 13:

Inserted text boxes for:

Dashboard Title

Company Name

Company Tagline

Step 14:

Inserted logo and rectangle shapes for a neat header section.

Step 15:

Published the report to Power BI Service.
