# FUTURE_DS_02 - Customer Retention & Churn Analysis

Future Interns, Data Science & Analytics track - Task 2.

## Objective
I analysed customer data from a subscription-based business to find churn patterns, key retention drivers and customer lifetime trends, and turned the results into recommendations to reduce customer loss.

## Data
- **Source:** "Telco Customer Churn" public sample dataset (Kaggle).
- **Size:** 7,043 customers, 21 columns (services, contract, billing, charges, tenure and a Churn Yes/No flag).
- **Quality checks:** I found no duplicate customers and no missing values, except 11 customers with 0 months tenure whose Total Charges were blank text. I set these to 0.
- **Limits of the data:** there is no churn-reason field and no sign-up or cancellation dates. Tenure (months as a customer) is the only time measure, so I show retention by tenure band rather than by sign-up cohort.

## Tools
Microsoft Excel (formulas and summary tables).

## Method
1. I added helper columns: Churn Flag, Tenure Band, Charge Band and a High-Risk Combo flag (month-to-month + fiber optic + electronic check).
2. I built summary tables with `COUNTIFS` and `SUMIFS` formulas: churn rate by tenure band, contract, internet service, payment method, charge band, support services and customer profile.
3. I used cross-tables to separate overlapping drivers, for example churn by contract within each tenure band, and by internet service within month-to-month customers.
4. I wrote up my findings and recommendations on the Insights sheet, each with its supporting numbers.

## Key numbers
| KPI | Value |
|---|---|
| Customers | 7,043 |
| Churned customers | 1,869 (26.5%) |
| Share of monthly charges lost to churn | 30.5% |
| Average tenure, churned vs retained | 18.0 vs 37.6 months |

## Key findings
1. **Early tenure:** churn is 52.9% in months 0-6 and falls to 9.5% after 48 months. First-year customers are 31% of the base but 55% of churners.
2. **Contract:** month-to-month customers churn at 42.7%, against 11.3% (one year) and 2.8% (two year). They are 88.6% of all churners.
3. **Fiber optic** churns at 41.9% against 19.0% for DSL, and the gap remains within month-to-month customers and after 12 months of tenure.
4. **Electronic check** payers churn at 45.3% against 15.2-19.1% for other methods, and still stand out among month-to-month customers.
5. **Support services:** customers with both Online Security and Tech Support churn at 9.0%; customers with neither churn at 49.0%.
6. **Profile:** seniors (41.7%), customers without a partner (33.0%) or dependents (31.3%) churn more. Gender makes no difference.
7. **Priority group:** month-to-month + fiber + electronic check is 18.6% of customers, churns at 60.4%, and accounts for 42.2% of all churners.
8. Churned customers pay more per month (74.44 vs 61.27), so I found that revenue is lost faster than customers.

## Recommendations
- I would run an onboarding and check-in plan for the first 6-12 months.
- I would offer incentives to move month-to-month customers onto one or two year contracts.
- I would investigate fiber optic service quality and pricing, for example with a customer survey.
- I would encourage automatic payment instead of electronic check.
- I would trial a Tech Support / Online Security bundle for new fiber customers and measure the result against a control group.
- I would build a priority outreach list for the month-to-month + fiber + electronic check group.
- I would record a cancellation reason and sign-up date for each customer, so future analysis can use real cohorts.

## Files
- `FUTURE_DS_02_Churn_Analysis.xlsx` - Data, Analysis and Insights sheets.
- `WA_Fn-UseC_-Telco-Customer-Churn.csv` - original dataset.

## Limitations
My analysis shows association, not proof of cause. Several drivers overlap (contract, fiber, payment method and tenure), so I do not add their effects together. Customers who buy add-on services may simply be more committed. My findings describe this dataset only.

## Note on tools
I used an AI assistant (Claude) to help build the workbook and draft the write-up. I reviewed the numbers and the findings myself.
