# HR Employee Attrition Analysis | Power BI Dashboard

An interactive two-page Power BI dashboard analysing why employees leave, built on the IBM HR Analytics Employee Attrition dataset (1,470 employees).

## Objective
Identify which employee groups have the highest attrition and which workplace factors are most strongly associated with employees leaving.

## Tools Used
- **Power BI Desktop**: dashboard design and interactivity
- **Power Query**: data cleaning and transformation
- **DAX**: KPI measures and calculated columns

## Data Preparation
- Validated data quality: 100% valid values, no missing or error values
- Removed 3 constant columns (EmployeeCount, Over18, StandardHours)
- Created an Age Group column (18–25, 26–35, 36–45, 46–55, 55+)
- Converted coded survey scores (1–4) into readable labels using DAX SWITCH
- Applied Sort by Column for logical category order

## DAX Measures
| Measure | Formula |
|---|---|
| Total Employees | `COUNTROWS(HR)` |
| Attrition Count | `CALCULATE(COUNTROWS(HR), HR[Attrition] = "Yes")` |
| Attrition Rate % | `DIVIDE([Attrition Count], [Total Employees], 0)` |
| Avg Monthly Income | `AVERAGE(HR[MonthlyIncome])` |

## Key Insights
- **Overall attrition rate: 16.12%** (237 of 1,470 employees)
- **Overtime:** 30.5% attrition with overtime compared with 10.4% without, about 3× higher
- **Work-life balance:** employees rating it "Bad" have the highest attrition (31.3%)
- **Business travel:** frequent travellers leave at about 3× the rate of non-travellers (24.9% vs 8.0%)
- **Income:** leavers earn about 30% less per month than stayers
- **Tenure:** about 25% of all leavers quit after just 1 year
- **Department:** Sales has the highest attrition *rate* (~20.6%), even though R&D has more leavers



## Recommendations
1. Monitor and limit overtime in high-attrition roles
2. Strengthen onboarding and support in the first two years
3. Review pay for entry-level roles
4. Track job satisfaction and work-life balance through regular surveys

## Files
- `HR_Attrition_Dashboard.pbix`: the Power BI dashboard file
- `N.Srijai_Power-BI_Report.pdf`: full project report
- `images/`: dashboard screenshots

## Dataset
[IBM HR Analytics Employee Attrition & Performance (Kaggle)](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

## Author
**N. Srijai**
[LinkedIn](www.linkedin.com/in/srijai-nimmagadda) · [Email](nimmagaddasrijai@gmail.com)
