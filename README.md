# Maximizing-DAX-Functions-in-Power-BI
The primary objective of this project is to showcase how Power BI's DAX capabilities can be leveraged to maximize analytical efficiency. By using this approach, businesses can enhance data interpretation, performance tracking, and strategic decision-making for improved outcomes.

###Dashboard Link:https://app.powerbi.com/groups/936e651d-45ad-4594-8f4e-6cabfc5765cc/reports/1215d961-b904-46e8-be0d-0e327aba8de9/add8766f3ba00e300c06?experience=power-bi

## Problem Statement

 Project Overview: Maximizing DAX Functions in Power BI
This project focuses on leveraging the power of DAX functions in Power BI to analyze and enhance business intelligence insights. The dataset contains four key columns, and the objective is to apply a wide range of DAX calculations to demonstrate advanced data modeling, aggregation, ranking, time intelligence, and filtering capabilities.

By implementing a variety of DAX measures and calculated columns, this project showcases how organizations can optimize reporting, enhance decision-making, and extract meaningful insights from structured data.

![Image](https://github.com/user-attachments/assets/c347f8b8-77c9-4876-8cae-469b3009d319)
### Key Challenges and Objectives:
Challenges
🔹 Maximizing DAX Function Usage – Implementing the widest range of DAX functions within a structured dataset.
🔹 Optimizing Performance – Ensuring that complex DAX measures are efficient and scalable.
🔹 Designing an Effective Report – Creating a well-structured and visually appealing Power BI report to showcase insights.
🔹 Balancing Simplicity & Complexity – Applying advanced DAX calculations while keeping the report user-friendly and insightful.

Objectives
✅ Showcase the Maximum Number of DAX Functions – Leverage aggregations, rankings, filtering, time intelligence, logical operations, and text functions.
✅ Design a Professional Power BI Report – Incorporate KPIs, dynamic visualizations, and interactive filters for meaningful insights.
✅ Ensure Actionable Insights – Enable users to interpret data trends, performance metrics, and key patterns using advanced DAX.
✅ Demonstrate Advanced DAX Capabilities – Illustrate the power of DAX by using nested functions, calculated columns, and measures effectively.

 The report was then published to Power BI Service.

 ### Steps followed 
 Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
 
#  *******DAX Functions*****

1.	Total sales = SUM(ProductData[Sales])

2.	Total Sales FreezeAll = CALCULATE([Total sales], ALL(ProductData))

3.	Growth% = [Total sales]/ [Total Sales FreezeAll]

4.	Growth% wrt Div = DIVIDE([Total sales],[Total Sales FreezeAll],"0")

5.	Total Product category = DISTINCTCOUNT(ProductData[Product Category])

6.	Total Product sub-category = DISTINCTCOUNT(ProductData[Product Sub Category])

7.	Total Sales Exclude/PC = CALCULATE([Total sales], ALLEXCEPT(ProductData, ProductData[Product Category]))

8.	Growth%wrt PC = [Total sales]/[Total Sales Exclude/PC]

9.	Total sales include = CALCULATE([Total sales], ALLSELECTED(ProductData))

10.	Growth% using ALLSelected = [Total sales]/ [Total sales include]

11.	Benchmark Sales 2012 = CALCULATE([Total sales], DateMaster[Year]=2012, ProductData[Product Category]= "AUDIO")

12.	FTD = FIRSTDATE(ProductData[Year])

13.	LTD = LASTDATE(DateMaster[Date])

14.	CALCULATE([Total sales], PREVIOUSYEAR(DateMaster[Date]))

15.	YoY% = DIVIDE( [Total sales]- [Prev Year Sale], [Prev Year Sale], "0")

16.	SPLY = CALCULATE([Total sales], SAMEPERIODLASTYEAR(DateMaster[Date])
Parallel Period wrt interval = 2years


17.	PP Sales = CALCULATE(sum(ProductData[Sales]), PARALLELPERIOD(DateMaster[Date],-2,YEAR))

18.	today = TODAY()


19.	Highest Sales = MAX(ProductData[Sales])

20.	Min Sales = MIN(ProductData[Sales])

21.	Avg Sales = AVERAGE(ProductData[Sales])

22.	No of Transactions = COUNT(ProductData[Sales])

23.	IF(<logical_test>, <value_if_true>[, <value_if_false>])

24.	<logical_test> RANKX(ALL(Products), SUMX(ssales), [SalesAmount])) 
<value_if_true> 
<value_if_false> blank () -------->returns blank Blanks are not equivalent to nulls. DAX uses blanks for both database nulls and for blank cells in Excel.


25.	Top 5 sales = IF(

26.	RANKX(ALL(ProductData[Product Sub Category]), [Total sales],,DESC) <= 5, 
[Total sales],
BLANK()
)


27.	DATESBETWEEN
2011 Sales = CALCULATE([Total sales], DATESBETWEEN(ProductData[Year], "1-1-2011","31-12-2011"))
2012 Sales = CALCULATE([Total sales], DATESBETWEEN(ProductData[Year], "1-1-2012","31-12-2012"))


 Project Files
 
Power BI Report (.pbix) – Contains the dataset and DAX measures.
Dataset (.csv/.xlsx) – Source data file.
README.md – Documentation of the project.

💡 Key Learnings
Effective use of DAX functions to analyze and manipulate data.
Applying ranking, filtering, and time intelligence in Power BI.
Understanding row-level vs. aggregate calculations in DAX.
