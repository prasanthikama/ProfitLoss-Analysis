# ProfitLoss-Analysis
Goal of this project  is to analyze profit and loss across financial, sales, and market perspectives.

This project focuses on understanding how much money we make and spend. We'll look at our finances, sales, and the market to figure out where we're making a profit and where we might be losing money. 
By doing this analysis, we aim to make smarter decisions that can help us earn more and improve our overall business success. Join us as we break down the numbers and find ways to boost our financial health.
p&L analyzing by segment,region,Net sales performance over time.
p&L analyzing by product and Total COGS

GM % = DIVIDE([GM $],[NS $],0)

Net Profit $ = [GM $]+[Operational Expense $]

Operational Expense $ = ('Key Measures'[Ads & Promotions $]+[Other Operational Expense $])*-1

P & L Final Value = 
SWITCH(TRUE(),
SELECTEDVALUE(fiscal_year[fy_desc])=MAX('P & L Columns'[Col Header]), [P & L values],
MAX('P & L Columns'[Col Header])="LY", [P & L LY],
MAX('P & L Columns'[Col Header])="YoY Chg",[P & L YoY Chg],
MAX('P & L Columns'[Col Header])="YoY Chg %",[P & L YoY Chg %]
)


Post Invoice Deduction $ = SUM(fact_actuals_estimates[post_invoice_deductions_amount])

Sales Qty = CALCULATE(
SUM(fact_actuals_estimates[Qty]),
fact_actuals_estimates[date]<=MAX(LastSalesMonth[LastSalesMonth]))

Total Post Invoice Deduction $ = 'Key Measures'[Post Invoice Deduction $] + 'Key Measures'[Post Invoice other Deduction $]

Top / Bottom N title = "Top / Bottom Products & Customers by " & 'Key Measures'[Selected P & L Row] 
