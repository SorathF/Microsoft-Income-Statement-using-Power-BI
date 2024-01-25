# Microsoft Income Statement Dashboard
## Introduction
This repository contains a Microsoft income statement dashboard created using Power BI. The dataset was downloaded from the official website of Microsoft.  
# Data Preparation
Initially, I created a template for line items in Excel, including line item number, description, and line item ID. Also, I prepared an income statement for the year 2023 in a separate worksheet. After that, I imported the file to Power BI.
# Data Analysis
I created new measures using DAX to calculate values for each line item:
-      Sales = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Revenue")
-      COGS = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Cost of Goods Sold")
-      Gross Profit = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Gross Profit")
-      Research and Development Expenses = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Research and Development Expenses")
-      Sales and Marketing Expenses = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Sales and Marketing Expenses")
-      General and Administrative Expenses = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "General and Administrative Expenses")
-      Operating Income = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Operating Income")
-      Other income = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Other income")
-      Income before Tax = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Income before Tax")
-      Income Tax = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Income Tax")
-      Net Income = CALCULATE(SUM('IS'[2023]), 'IS'[Line Item] = "Net Income")
For calculations of the year 2022, I changed the year in the above formulas. Furthermore, I created another measure to pull the correct values for each line item.
-     FY'23 = SWITCH(SELECTEDVALUE(Sheet1[Line Item ID]),
      "Sales", [Sales],
      "Cost of Goods Sold", [COGS],
      "Gross Profit", [Gross Profit],
      "OPEX-Research and Development Expenses", [Research and Development Expenses],
      "OPEX_Sales and Marketing Expenses", [Sales and Marketing Expenses],
      "OPEX-General and Administrative Expenses", [General and Administrative Expenses],
      "Operating Income", [Operating Income],
      "Other income", [Other income],
      "Income before Tax", [Income before Tax],
      "Income Tax", [Income Tax],
      "Net Income", [Net Income])
  Repeated the same for FY'22 values.
  ## Data Visualization
  You can find my dashboard [here](https://www.novypro.com/project/microsoft-income-statement-dashboard-power-bi)
 ![Dashboard](https://github.com/SorathF/Microsoft-Income-Statement-using-Power-BI/assets/154694595/04143911-8a7e-45fb-b4a6-931d656a6f80)
