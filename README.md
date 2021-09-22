# Personal-finance-management
## INSIGHT OF YOUR PERSONAL FINANCE MANAGEMENT

Creating a Report to validate and have a deep understanding abut the personal finance how much income you have
and how much of that is spend as expense and in which forms and the savings

Dataset `Finance Database.xlsx` Excel file is used in this project

Data analysis in this project is mainly done in Power Query and Report is created in Power BI 

A column `Year` is created in power Query by Unpivoting all the date columns

## Data Analysis Using POWER BI 

1 . Formula used to create new measure Total income 

 `Total income = CALCULATE(SUM(FinData[Value]),FinData[Type]="Income")`
 
2 . Formula used to create new measure Total expense 

  `Total Expenses = CALCULATE(SUM(FinData[Value]),FinData[Type]="Expense")`

3 . Formula used to create new meausre Totak savings

  `Total Savings = CALCULATE(SUM(FinData[Value]),FinData[Type]="Savings")`
   
4 . FOrmula used to create new measure Expense %

  `Expense % = DIVIDE([Total Expenses],[Total income])`
    
5 . Formula used to create new measure Savings % 

  `Savings % = DIVIDE([Total Savings],[Total income])`
    
6 . Formula used to create new measure Values

  `Values = SUM(FinData[Value])`
     
7 . Formula used to create new measure Income LM ( last month )

  `income LM = CALCULATE([Total income],DATEADD(FinData[Date],-1,MONTH))`
    
8 . Formula used to create new measure Income change MoM %

  `Income change MoM % = DIVIDE([Total income],[income LM])`
    
9 . Formula used to create new measure Savings Target

  `Savings target = 0.25`
     
10 . Formula used to create new measure  Cumulative net worth 

  `Cumulative net worth = CALCULATE([Total Savings],FILTER(ALL(FinData[Date]),FinData[Date] <= MAX(FinData[Date])))`
  
  
  
  
  ### ToolTips 
  
 1 . Tooltip included for Expense for each component as line chart 
 
 2 . Tooltip included for Savings for each component as line chart  
 
 3 . Tooltip included for Cumulative net worth per date  as line chart
 
 4 . Tooltip included for expense to income comparison as line and clusterd column chart 
